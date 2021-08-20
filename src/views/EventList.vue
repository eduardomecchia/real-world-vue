<template>
  <h1>Events For Good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from '@/components/EventCard.vue'
import axios from 'axios'

export default {
  name: 'EventList',
  components: {
    EventCard
  },

  data() {
    return {
      events: null
    }
  },

  created() {
    const api = "https://my-json-server.typicode.com/eduardomecchia/real-world-vue-db/events";
    axios.get(api);
  }
}
</script>

<style scoped>
  .events {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>