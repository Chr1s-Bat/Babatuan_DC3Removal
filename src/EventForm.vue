<template>
  <form @submit.prevent="handleSubmit">
    <h2>Event Registration Form</h2>
    
    <div>
      <label for="name">Participant Name:</label>
      <input type="text" id="name" v-model="participantName" required />
    </div>

    <div>
      <label for="studentId">Student ID:</label>
      <input type="text" id="studentId" v-model="studentId" required />
    </div>

    <div>
      <label for="event">Event:</label>
      <select id="event" v-model="selectedEvent" required>
        <option disabled value="">Select an Event</option>
        <option value="IT Week">IT Week</option>
        <option value="Technology Summit">Technology Summit</option>
        <option value="Student Leadership Seminar">Student Leadership Seminar</option>
      </select>
    </div>

    <div>
      <label>Attendance Type:</label>
      <label>
        <input type="radio" value="On-site" v-model="attendanceType" required /> On-site
      </label>
      <label>
        <input type="radio" value="Online" v-model="attendanceType" required /> Online
      </label>
    </div>

    <div>
      <label for="email">Email:</label>
      <input type="email" id="email" v-model="email" required />
    </div>

    <button type="submit">Register for Event</button>
  </form>
</template>

<script setup>
import { ref } from 'vue'

// Define reactive data using ref()
const participantName = ref('')
const studentId = ref('')
const selectedEvent = ref('')
const attendanceType = ref('')
const email = ref('')

// Define custom events using defineEmits()
const emit = defineEmits(['event-submitted'])

const handleSubmit = () => {
  // Package form data into an object
  const registrationData = {
    participantName: participantName.value,
    studentId: studentId.value,
    event: selectedEvent.value,
    attendanceType: attendanceType.value,
    email: email.value
  }

  // Emit the custom event with the object data
  emit('event-submitted', registrationData)
}
</script>