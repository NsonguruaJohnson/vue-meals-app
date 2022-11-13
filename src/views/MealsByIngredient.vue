<template>
  <Meals :meals="meals"/>
</template>

<script setup>
  import { computed, onMounted, ref } from "vue";
import Meals from '../components/Meals.vue';
  import { useRoute } from "vue-router";
  import store from "../store";

  const route = useRoute();
const meals = computed(() => store.state.mealsByIngredient)
    
  onMounted(() => {
    store.dispatch('searchMealsByIngredient', route.params.ingredient)
  })
</script>

<style>

</style>