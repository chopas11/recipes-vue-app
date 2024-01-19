<script setup>

import Welcome from "./widgets/Welcome/Welcome.vue";
import Header from "./widgets/Header/Header.vue";
import Footer from "./widgets/Footer/Footer.vue";
import RecipesList from "./components/RecipesList/RecipesList.vue";
import Weeks from "./widgets/Weeks/Weeks.vue";
import Kitchen from "./widgets/Kitchen/Kitchen.vue";

const kitchens = [
  {
    id: 1,
    label: "Итальянская кухня",
    description: "<p>В основе итальянской кухни лежат исторически сложившиеся многовековые традиции с культурными влияниями <b>римлян, греков, лангобардов, арабов</b> и прочих народов, когда-либо населявших Италию или оказывавших влияние на формирование её культуры.</p>",
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
]

</script>

<template>
  <div class="wrapper container mx-auto">
    <Header />
    <Welcome />
    <h2>фавориты наших пользователей</h2>
    <RecipesList />
    <h2>Неделя Италии</h2>
    <Weeks />
    <h2><span class="text-6xl lowercase">tut</span> собрано более 1000 рецептов 2 кухонь</h2>
    <Kitchen v-for="kitchen in kitchens" :label="kitchen.label" :dishes="kitchen.dishes" :color="kitchen.color" >{{ kitchen.description }}</Kitchen>

    <Footer />
  </div>

</template>

<style scoped>

</style>
