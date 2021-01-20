<template>
  <div class='booking-card'>
      
      <h2>Customer name: {{booking.name}}</h2>
      <p>{{booking.email}}</p>
      <p>{{booking.status}}</p>

<button v-on:click='deleteBooking'>Delete</button>

      <!-- ADD DELETE BUTTON (also remember the method)-->


  </div>
</template>

<script>
import {eventBus} from '@/main.js'
import bookingService from '@/services/bookingService.js'

export default {
    name: 'booking',
    props: ['booking'],
    methods: {
        deleteBooking(){
            bookingService.deleteBooking(this.booking._id)
            .then(() => )
        }
    }
}
</script>

<style>

</style>