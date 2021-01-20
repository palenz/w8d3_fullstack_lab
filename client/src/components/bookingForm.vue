<template lang='html'>
        <form v-on:submit.prevent='addBooking'>
            <label for='name'>Name:</label>
            <input type='text' id='name' v-model='name'></input>
            <label for='email'>Email:</label>
            <input type='text' id='email' v-model='email'></input>
            <label for='status'>Client status:</label>
                <select name='status' id='status' v-model='status'>
                    <option value='notCheckedIn' selected="selected">Client has not checked in</option>
                    <option value='checkedIn'>Client has checked in</option>
                    <option value='checkedOut'>Client has checked out</option>
                </select>
            <input type="submit"/>
        </form>
</template>

<script>
import bookingService from '@/services/bookingService.js'
import { eventBus } from '@/main.js'

export default {
    name: 'booking-form',
    data(){
        return{
            name: null,
            email: null,
            status: null
        }
    },
    methods: {
        addBooking(){
            const booking = {
                name: this.name,
                email: this.email,
                status: this.status
            }    
        bookingService.postBooking(booking)
        .then (res => eventBus.$emit ('booking-added', res))
        }
    }


}
</script>

<style>

</style>