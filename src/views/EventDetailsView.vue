<script setup>
import { ref, onMounted } from 'vue'
import EventService from '@/services/EventService.js'

const props = defineProps({
  id: {
    required: true,
  },
})

const event = ref(null)

onMounted(() => {
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
  <div class="detailsView" v-if="event">
    <img :src="event.image" alt="">
    <h1>{{ event.name }}</h1>
    <p>Job | {{ event.job }} </p>
    <p>Skills | {{ event.skills }}</p>
    <p>Language: {{ event.language }}</p>
    <p>Address | {{ event.city }}</p>
    <p>{{ event.email }}</p>
  </div>
</template>

