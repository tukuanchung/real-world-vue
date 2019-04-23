<template>
  <div>
    <h1>Events Listing</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event"/>
    <!-- <EventCard/> -->
    <!-- <p>

    </p>-->
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
import axios from 'axios'
import EventService from '@/services/EventService.js'

export default {
  data() {
    return {
      events: []
    }
  },
  components: {
    EventCard
  },
  created() {
    // axios
    // .get('http://localhost:3000/events') // Does a get request
    EventService.getEvents()
      .then(response => {
        this.events = response.data
        console.log(response.data) // For now, logs out the response
      })
      .catch(error => {
        console.log('There was an error:', error.response) // Logs out the error
      })
  }
}
</script>