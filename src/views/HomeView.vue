<script setup>
import { ref } from 'vue'
import EcentCard from '@/components/EventCard.vue'

const events = ref([
  {
    id: 436546,
    category: 'Automobile',
    title: 'Bmw M5 Compition',
    descr: 'One of the best car in the world.',
    location: 'Dushanbe City',
    date: 'March 23, 2023',
    time: '13:00',
    petsAllowed: 'true',
    organizer: 'Mikel Angelos'
  },
  {
    id: 217899,
    category: 'Automobile',
    title: 'Rolls Royce',
    descr: 'A luxury car for a luxury lover.',
    location: 'Moscow City',
    date: 'August 11, 2023',
    time: '09:00',
    petsAllowed: 'true',
    organizer: 'Kesedy'
  },
  {
    id: 567464,
    category: 'Automobile',
    title: 'GMC Considering',
    descr: 'For the most insane.',
    location: 'Texas City',
    date: 'August 02, 2012',
    time: '06:00',
    petsAllowed: 'true',
    organizer: 'Jack NewMan'
  }
])
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
  flex-direction: column;
  align-items: center;
}
</style>
