<template>
  <div class="movie-detail container">
    <h2 class="text-center">{{movie.Title}}</h2>
    <p class="text-center">{{ movie.Year }}</p>
    <img :src="movie.Poster" alt="Movie Poster" class="featured-img" />
    <p class="text-center">{{ movie.Plot }}</p>
  </div>
</template>

<script>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';
import env from '@/env.js';
export default {
  setup () {
    const movie = ref({});
    const route = useRoute();
    onBeforeMount(() => {
      fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`)
        .then(response => response.json())
        .then(data => {
          movie.value = data;
        });
    });
    return {
      movie
    }
  }
}
</script>

<style lang="scss">
.movie-detail {
  padding: 16px;
  display: flex!important;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;

  h2 {
    color: #FFF;
    font-size: 28px;
    font-weight: 600;
    margin-bottom: 16px;
  }
  .featured-img {
    display: block;    
    margin-bottom: 32px;
  }
  p {
    color: #FFF;
    font-size: 18px;
    line-height: 1.4;
  }
}
</style>