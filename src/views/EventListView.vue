<script setup>
import EventCard from '@/components/EventCard.vue';
import {ref, onMounted} from 'vue';
import EventService from '@/services/EventService';

const events = ref(null)
onMounted(()=>{
  EventService.getEvents()
  .then((response)=>{
    events.value = response.data
  })
  .catch((error)=>{
    console.log(error)
  })
})
</script>

<template>
    <h1>People to work with</h1>

  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<style scoped>
.events{
  display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    grid-gap: 20px;
    padding: 20px;
}
</style>