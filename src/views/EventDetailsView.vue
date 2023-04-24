<script setup>
import { ref, onMounted } from 'vue'
import EventService from '../services/EventService.js'

const props = defineProps({
  id: {
    required: true
  }
})
const event = ref(null)

onMounted(() => {
  // fetch event (by id) and set local data
  EventService.getEvent(props.id)
    .then((response) => {
      event.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
</script>

<template>
  <div v-if="event">
    <h1 class="title">{{ event.title }}</h1>
    <img class="car-size" :src="event.img" alt="" />
    <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
    <p>{{ event.descr }}</p>
  </div>
</template>

<style>
.car-size {
  width: 700px;
}

.title {
  font-size: 32px;
}

@media (max-width: 768px) {
  .title {
    font-size: 20px;
  }
}

@media (max-width: 760px) {
  .car-size {
    width: 300px;
  }
}
</style>
