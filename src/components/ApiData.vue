<template>
  <div class="api-data">
    <h2>Random Anime Quote</h2>
    <button @click="fetchData">Fetch Quote</button>
    <div v-if="animeData">
      <p><span>ID:</span> {{ animeData.id }}</p>
      <p><span>Quote:</span> {{ animeData.quote }}</p>
      <p> <span>Anime:</span> {{ animeData.anime }}</p>
      <p><span>Character:</span>  {{ animeData.character }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';

const animeData = ref(null);

const fetchData = async () => {
  try {
    const response = await axios.get('https://animechan.xyz/api/random');
    animeData.value = response.data;
  } catch (error) {
    console.error(error);
  }
};
</script>
