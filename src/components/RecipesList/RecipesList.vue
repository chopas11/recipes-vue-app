<script>
import RecipeCard from "../RecipeCard/RecipeCard.vue";

export default {
  name: "RecipesList",
  components: {RecipeCard},
  props: {
    recipes: {
      type: Array,
      required: true,
    }
  },
}
</script>

<template>
  <div class="recipes flex flex-row mt-10 flex-wrap">
    <RecipeCard v-for="recipe in recipes" :likes="recipe.likes" :views="recipe.views" :ingredients="recipe.ingredients"
                :time="recipe.time" :label="recipe.label" :image="recipe.image" />
  </div>
</template>

<style scoped>

</style>