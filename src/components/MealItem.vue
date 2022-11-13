<template>
  <div
    class="bg-white shadow rounded-xl"
    >
    <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
      <img :src="meal.strMealThumb" :alt="meal.strMeal" class="rounded-t-xl w-full h-48 object-cover">
    </router-link>
    <div class="p-3">
      <h3 class="font-bold">{{ meal.strMeal }}</h3>
      <p class="mb-4">
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Delectus deleniti id, nobis nam mollitia veritatis reprehenderit ab assumenda qui dolor doloremque
        in ex quod aspernatur exercitationem voluptates corrupti vitae repudiandae?
      </p>
      <div class="flex items-center justify-between">
        <!-- <youtube-button :href="meal.strYoutube"/> -->
        <YoutubeButton :href="meal.strYoutube">
          YouTube
        </YoutubeButton>
      </div>
    </div>
  </div>
</template>

<script setup>
  import YoutubeButton from '../components/YoutubeButton.vue';

  const { meal } = defineProps({
    meal: {
      required: true,
      type: Object,
    }
  })
</script>

<style>

</style>