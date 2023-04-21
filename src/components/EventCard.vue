<script setup>
defineProps({
  event: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <RouterLink :to="{ name: 'event-details', params: { id: event.id } }">
    <div class="event-card">
      <img :src="event.image" alt="">
      <h3 class="event-link">{{ event.name }}</h3>
      <span class="event-link">{{ event.city }} | {{ event.skills }}</span>
    </div>
  </RouterLink>
</template>

<style scoped>
.event-card {
  padding: 20px;
  cursor: pointer;
  margin-bottom: 18px;
  transition: .3s all;
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
a:link { text-decoration: none; }

.event-link {
  color: #2c3e50;
  text-decoration: none;
}


</style>
