<script setup>
import { ref, onMounted } from 'vue'
import EventService from '@/services/EventService.js'
import EcentCard from '@/components/EventCard.vue'

const events = ref(null)

onMounted(() => {
  EventService.getEvents()
    .then((response) => {
      events.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
</script>

<template>
  <h1>There is a card of 3 car models</h1>

  <div class="events">
    <EcentCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<style scoped>
.events {
  display: flex;
  justify-content: center;
  align-items: center;
}

@media (max-width: 768px) {
  .events {
    display: flex;
    flex-direction: column;
  }
}
</style>
