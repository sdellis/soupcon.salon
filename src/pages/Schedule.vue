<template>
  <Layout>
    <article>
    <h1>Schedule of Events</h1>
    <p class="important-note"><em>Are you a Soupçon Salon partner (aka, "member") and have a great idea for an event? <a href="https://docs.google.com/forms/d/e/1FAIpQLSeKQ_bnHmbhXHlhXxc3BXQYwkzW-Kz4nGTY0khFH06PJUs5kw/viewform">Propose your event here</a> and we'll work with you to get it on the schedule!</em></p>
    <p class="note"><strong>Co-Working at the Firehouse takes place Monday through Friday from 9:00am to 5:00pm. Open to all Partners and includes use of printers and Wi-Fi.</strong>
    <br/>Please keep an eye on the Partners email list for cancelations, or reach out to that list for more info.</p>
    <!-- <h2>Events will resume once we make necessary repairs to the building. Thanks for your patience!</h2> -->
    <div v-for="slot in schedule($page.events.edges)" :key="slot.year">
      <h2>{{ slot.month }} {{ slot.year }}</h2>

      <div class="month" v-for="event in slot.events" :key="event.id">
        <div v-bind:class="{ pending: !event.event.approved }">
          <p v-if="!event.event.approved" class="tag">Pending</p>
          <h3><a :href="event.event.path">{{ event.event.title }}</a></h3>
          <h4>{{ formatDate(event.event.date) }}</h4>
          <p>{{ event.event.abstract }}</p>
        </div>
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
        approved
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
  margin-right: 4em;
  padding: .5em .5em .5em .5em;
}

.pending {
  opacity: .5;
}

.month:nth-of-type(odd) {
  background: aliceblue;
}

.important-note {
  background: beige;
  padding: 1em;
}

.note {
  padding: 1em;
}

.tag {
  background-color: gray;
  border: 1px solid darkgray;
  border-radius: 2em;
  color: white;
  display: inline-block;
  font-size: 12px;
  font-weight: 500;
  padding: 0 6px;
  text-align: center;
}
</style>
