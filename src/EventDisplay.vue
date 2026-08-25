<template>
  <div v-if="registration">
    <h3>Event Registration</h3>
    <p><strong>Participant Name:</strong> {{ registration.participantName }}</p>
    <p><strong>Student ID:</strong> {{ registration.studentId }}</p>
    <p><strong>Event:</strong> {{ registration.event }}</p>
    <p><strong>Attendance Type:</strong> {{ registration.attendanceType }}</p>
    <p><strong>Email:</strong> {{ registration.email }}</p>
  </div>
</template>

<script setup>
// Define props to receive data from App.vue
defineProps({
  registration: {
    type: Object,
    default: null
  }
})
</script>