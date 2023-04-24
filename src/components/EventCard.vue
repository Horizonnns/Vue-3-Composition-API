<script setup>
defineProps({
  event: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <section class="cards">
    <RouterLink class="event-link" :to="{ name: 'event-details', params: { id: event.id } }">
      <div class="event-card">
        <img :src="event.img" alt="automobiles" class="cars" />

        <!-- Display event data -->
        <h2 class="title">{{ event.title }}</h2>
        <span>@{{ event.time }} on {{ event.date }}</span>
      </div>
    </RouterLink>
  </section>
</template>

<style scoped>
.cars {
  width: 220px;
}

.event-card {
  padding-top: 20px;
  padding-bottom: 20px;
  margin: 10px;
  width: 250px;
  height: 240px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
  background-size: auto;
  background-position: center;
}

.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}

.event-link {
  color: #2c3e50;
  text-decoration: none;
}
</style>
