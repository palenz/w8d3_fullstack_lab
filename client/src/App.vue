<template>
  <div>

    <booking-form/>
    <booking-grid/>

  </div>
</template>

<script>
import bookingForm from './components/bookingForm.vue';
import bookingGrid from './components/bookingGrid.vue';



export default {
  name: 'app',
  components: {
    'booking-form': bookingForm,
    'booking-grid': bookingGrid
    },
}
</script>

<style>

</style>
