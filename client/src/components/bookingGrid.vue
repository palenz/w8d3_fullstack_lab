<template>
  <div>
      <booking v-for='(booking, index) in bookings' :key='index' :booking='booking'></booking>
  </div>
</template>

<script>
import booking from './booking.vue'
import bookingService from '@/services/bookingService.js'
import {eventBus} from '../main.js'

export default {
    name: 'booking-grid',
    data (){
        return{
            bookings: []
        };
    },
    mounted(){
        bookingService.getBookings()
        .then(bookings => this.bookings = bookings);

        eventBus.$on('booking-added', (booking) => {
            this.bookings.push(booking)
        })
    },
    components: {
        'booking': booking
    }
}

</script>

<style>

</style>