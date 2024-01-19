<script>
import RecipeCard from "../RecipeCard/RecipeCard.vue";

import image1 from "../../assets/images/recipe-1.png"
import image2 from "../../assets/images/recipe-2.png"
import image3 from "../../assets/images/recipe-3.png"
import image4 from "../../assets/images/recipe-4.png"

export default {
  name: "RecipesList",
  components: {RecipeCard},
   data () {
     return {
       recipes: [
         {
           id: 1,
           label: "Шоколадный Брауни",
           time: 40,
           ingredients: 6,
           views: 1200,
           likes: 500,
           image: image1,
         },
         {
           id: 2,
           label: "Пицца со страчателлой",
           time: 80,
           ingredients: 8,
           views: 2000,
           likes: 780,
           image: image2,
         },
         {
           id: 3,
           label: "Крылышки Барбекю",
           time: 30,
           ingredients: 4,
           views: 997,
           likes: 460,
           image: image3,
         },
         {
           id: 4,
           label: "Паста Болоньезе",
           time: 35,
           ingredients: 5,
           views: 2800,
           likes: 900,
           image: image4,
         },
       ]
     }
   }
}
</script>

<template>
  <div class="recipes flex flex-row gap-3 mt-10">
    <RecipeCard v-for="recipe in recipes" :likes="recipe.likes" :views="recipe.views" :ingredients="recipe.ingredients"
                :time="recipe.time" :label="recipe.label" :image="recipe.image" />
  </div>
</template>

<style scoped>

</style>