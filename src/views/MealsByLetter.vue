<template>
  <div class="flex justify-center gap-2 mt-2">
    <router-link :to="{ name: 'byLetter', params: { letter } }" v-for="letter of letters" :key="letter">
      {{ letter }}
    </router-link>
  </div>
  
  <meals :meals="meals"></meals>
</template>

<script setup>
  import { computed, onMounted, watch } from 'vue';
import Meals from '../components/Meals.vue';
  import { useRoute } from 'vue-router';
  import store from '../store';

  const route = useRoute();
  const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('');
  const meals = computed(() => store.state.mealsByLetter);

  watch(route, () => {
    store.dispatch('searchMealsByLetter', route.params.letter)
  })

  onMounted(() => {
    store.dispatch('searchMealsByLetter', route.params.letter)
  })

</script>

<style>

</style>