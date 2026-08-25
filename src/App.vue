<template>
  <div id="app">
    <!-- Listen for event-submitted custom event -->
    <EventForm @event-submitted="handleRegistration" />
    
    <!-- Pass stored registration info to EventDisplay via props -->
    <EventDisplay :registration="storedRegistration" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import EventForm from './EventForm.vue'
import EventDisplay from './EventDisplay.vue'

// Store received registration information using ref()
const storedRegistration = ref(null)

const handleRegistration = (data) => {
  storedRegistration.value = data
}
</script>