<script>

import image1 from "../../assets/images/welcome-1.png"
import image2 from "../../assets/images/welcome-2.png"
import image3 from "../../assets/images/welcome-3.png"
import image4 from "../../assets/images/welcome-4.png"
import Button from "../../components/Button/Button.vue";
import StarIcon from "../../assets/Icons/StarIcon/StarIcon.vue";

export default {
  name: "Welcome",
  components: {StarIcon, Button},
  data: function () {
    return {
      image1: image1,
      image2: image2,
      image3: image3,
      image4: image4,
    }
  }
}
</script>

<template>
  <div class="welcome p-20">
    <div class="welcome_images flex flex-row gap-4">
      <img class="w-40" :src="image1" alt="Welcome-1" />
      <img class="w-40" :src="image2" alt="Welcome-2" />
      <img class="w-40" :src="image3" alt="Welcome-3" />
      <img class="w-40" :src="image4" alt="Welcome-4" />
    </div>
    <div class="welcome_description flex flex-row justify-between pt-20">
      <div class="relative">
        <h1 class="font-bold uppercase geologica">Сайт-сборник</h1>
        <span class="text-white font-medium mb-2">Итальянская и американская кухня</span>
        <div class="pt-10">
          <Button>Добавить рецепт</Button>
        </div>
      </div>
      <div class="flex flex-row basis-1/4 gap-2">
        <div>
          <StarIcon />
        </div>
        <p class="font-medium">Все рецепты мы проверили сами и подобрали правильные граммовки</p>
      </div>
    </div>
  </div>
</template>

<style scoped>

.welcome {
  background: var(--lil-color);
  border-radius: 80px;
}

</style>