<template>
  <Layout>
    <div class="calendar" style="grid-column: 2 / span 1;">
        <h1>Calendar of Menus and Events</h1>
        <CalendarMonth v-bind:events="cleanEvents($page.events.edges)" />
    </div>
  </Layout>
</template>
<page-query>
query {
  events: allEvents {
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
import CalendarMonth from "../components/CalendarMonth";

export default {
  metaInfo: {
    title: 'Soupçon Salon - Calendar'
  },
  components: {
    CalendarMonth
  },
  methods: {
      cleanEvents: function (dirtyEvents) {
        const e = JSON.parse(JSON.stringify(dirtyEvents))
        var cleanEvents = []
        for (var key in e) {
            cleanEvents.push(e[key].node)
        }
        return cleanEvents
      },
  }
};
</script>

<style>
.calendar {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;

  font-weight: 100;
  --grey-100: #e4e9f0;
  --grey-200: #cfd7e3;
  --grey-300: #b5c0cd;
  --grey-800: #3e4e63;
  --grid-gap: 1px;
  --day-label-size: 20px;
}

ol,
li {
  padding: 0;
  margin: 0;
  list-style: none;
}

.calendar-month-header {
  display: flex;
  justify-content: space-between;
  background-color: #fff;
  padding: 10px;
}
</style>
