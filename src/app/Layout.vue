<script>
import AddRecipe from "../widgets/AddRecipe/AddRecipe.vue";
import Footer from "../widgets/Footer/Footer.vue";
import Header from "../widgets/Header/Header.vue";
import Welcome from "../widgets/Welcome/Welcome.vue";
import RecipesList from "../components/RecipesList/RecipesList.vue";
import Kitchen from "../widgets/Kitchen/Kitchen.vue";
import Weeks from "../widgets/Weeks/Weeks.vue";
import SearchRecipes from "../widgets/SearchRecipes/SearchRecipes.vue";
import image1 from "../assets/images/recipe-1.png";
import image2 from "../assets/images/recipe-2.png";
import image3 from "../assets/images/recipe-3.png";
import image4 from "../assets/images/recipe-4.png";

export default {
  name: "Layout",
  components: {SearchRecipes, Weeks, Kitchen, RecipesList, Welcome, Header, Footer, AddRecipe},
  data () {
    return {
      kitchens: [
        {
          id: 1,
          label: "Итальянская кухня",
          description: "В основе итальянской кухни лежат исторически сложившиеся многовековые традиции с культурными влияниями <b>римлян, греков, лангобардов, арабов</b> и прочих народов, когда-либо населявших Италию или оказывавших влияние на формирование её культуры.",
          dishes: "Макаронные изделия, пицца, ризотто, лазанья, ньокки, равиоли, чиабатта, полента, минестроне, фритатта",
          color: "green-light",
        },
        {
          id: 2,
          label: "Американская кухня",
          description: "Начавшись с традиций английской кухни <b>XVII—XVIII</b> веков, смешавшихся с некоторыми кулинарными традициями американских индейцев, она значительно менялась в течение последних трёх столетий, став <b>синтезом</b> кулинарных традиций всего мира, сочетающим кухни различных иммигрантских культур.",
          dishes: "Гамбургеры, клэм-чаудер, чили кон карне, банановый хлеб, томатный суп, тыквенный и пекановый пироги, брауни, пончики, маффины,чизкейки.",
          color: "lil-light",
        },
      ],
      mainVisible: true,
      addRecipesVisible: false,
      searchVisible: false,
      searchQuery: "",
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
  },
  methods: {
    showAddRecipes () {
      this.mainVisible = false;
      this.addRecipesVisible = true;
    },
    showSearchRecipes () {
      this.mainVisible = false;
      this.addRecipesVisible = false;
      this.searchVisible = true;
    },
    backToMain () {
      this.mainVisible = true;
      this.addRecipesVisible = false;
      this.searchVisible = false;
    },
    updateSearchQuery (query) {
      this.searchQuery = query;
    },
  },
  created() {
    if (localStorage.getItem("recipes") === null) {
      console.log("Recipes is Null!");
      localStorage.setItem('recipes', JSON.stringify([...this.recipes]));
    }
  }
}
</script>

<template>
  <div class="wrapper">
    <div class="content container mx-auto relative">
      <Header @search="updateSearchQuery" @show="showSearchRecipes" />
      <AddRecipe @back="backToMain" v-if="addRecipesVisible" />
      <SearchRecipes @back="backToMain" v-if="searchVisible" :query="searchQuery" />

      <div v-if="mainVisible">
        <Welcome @show="showAddRecipes" />
        <h2>фавориты наших пользователей</h2>
        <RecipesList :recipes="recipes" />
        <h2>Неделя Италии</h2>
        <Weeks />
        <h2><span class="text-6xl lowercase">tut</span> собрано более 1000 рецептов 2 кухонь</h2>
        <Kitchen v-for="kitchen in kitchens" :label="kitchen.label" :dishes="kitchen.dishes"
                 :color="kitchen.color" :description="kitchen.description" />
      </div>
    </div>
    <Footer />
  </div>

</template>

<style scoped>
.wrapper {
  height: calc(100vh - 70px);
}

.content {
  box-sizing: border-box;
  min-height: 100%;
  padding-bottom: 60px;
}
</style>