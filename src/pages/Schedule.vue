<template>
  <Layout>
    <article>
    <h1>Schedule of Events</h1>
    <p><em>Are you a Soupçon Salon partner (aka, "member") and have a great idea for an event? <a href="https://docs.google.com/forms/d/e/1FAIpQLSeKQ_bnHmbhXHlhXxc3BXQYwkzW-Kz4nGTY0khFH06PJUs5kw/viewform">Propose your event here</a> and we'll work with you to get it on the schedule!</em></p>
    <div v-for="slot in schedule($page.events.edges)" :key="slot.year">
      <h2>{{ slot.month }} {{ slot.year }}</h2>
      <div class="month" v-for="event in slot.events" :key="event.id">
        <h3><a :href="event.event.path">{{ event.event.title }}</a></h3>
        <h4>{{ formatDate(event.event.date) }}</h4>
        <p>{{ event.event.abstract }}</p>
      </div>
    </div>
  </article>
  </Layout>
</template>
<page-query>
query {
  events: allEvents(sortBy: "date", order: DESC) {
    edges {
      node {
        title
        performer
        abstract
        image
        path
        date
      }
    }
  }
}
</page-query>
<script>
import dayjs from "dayjs"
export default {
  metaInfo: {
    title: 'Soupçon Salon - Schedule of Events'
  },
  methods: {
      formatDate: function (d) {
        return dayjs(d).format('dddd, MMMM DD @h:mma')
      },
      schedule: function (dirtyEvents) {
        const e = JSON.parse(JSON.stringify(dirtyEvents))
        var cleanEvents = []
        for (var key in e) {
          // if(dayjs().isBefore(dayjs(e[key].date))){
          //   cleanEvents.push(e[key].node)
          // }
          cleanEvents.push(e[key].node)
        }
        const sched = Object.values(cleanEvents.reduce( (acc,evt) => {
            const key = `${dayjs(evt.date).format('YYYY')}-${dayjs(evt.date).format('MMMM')}`;
            if(dayjs().isBefore(dayjs(evt.date))){
              if(!acc[key]) {
                acc[key] = {year: dayjs(evt.date).format('YYYY'), month: dayjs(evt.date).format('MMMM'), events:[]}
              }
              acc[key].events.unshift( {event:evt} );
            }
            return acc;
          },{})
        );
        return sched.reverse()
      },
  }
};
</script>

<style>
.month {
  margin-left: 2em;
}
</style>
