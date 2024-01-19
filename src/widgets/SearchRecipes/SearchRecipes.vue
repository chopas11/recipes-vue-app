<script>
import Button from "../../components/Button/Button.vue";
import RecipeCard from "../../components/RecipeCard/RecipeCard.vue";
import RecipesList from "../../components/RecipesList/RecipesList.vue";

export default {
  name: "SearchRecipes",
  components: {RecipesList, RecipeCard, Button},
  props: {
    query: {
      type: String,
      required: true,
    }
  },
  computed: {
    recipes () {
      const arr = JSON.parse(localStorage.getItem('recipes'));
      return arr.filter(item => item.label.toLowerCase().includes(this.query.toLowerCase()));
    }
  },

}
</script>

<template>
  <div class="searchRecipes">
    <div class="text-center">
      <h2>Результаты поиска</h2>
      <RecipesList :recipes="recipes" />
      <div class="mt-20">
        <Button @click="this.$emit('back')" styles="green">Вернуться на главную</Button>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>