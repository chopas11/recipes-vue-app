<script>
import ClockIcon from "../../assets/Icons/ClockIcon/ClockIcon.vue";
import EyeIcon from "../../assets/Icons/EyeIcon/EyeIcon.vue";
import LikeIcon from "../../assets/Icons/LikeIcon/LikeIcon.vue";

export default {
  name: "RecipeCard",
  components: {LikeIcon, EyeIcon, ClockIcon},
  props: {
    label: {
      type: String,
      required: true,
    },
    time: {
      type: Number,
      required: true,
    },
    ingredients: {
      type: Number,
      required: true,
    },
    views: {
      type: Number,
      required: true,
    },
    likes: {
      type: Number,
      required: true,
    },
    image: {
      type: String,
      required: false,
    }
  }
}
</script>

<template>
  <div class="recipe_wrapper basis-1/4">
    <div class="recipe">
      <img :src="image" alt="Image" class="rounded-3xl">
      <div class="recipe_description">
        <div class="text-center mt-5">
          <h3 class="text-lg uppercase">{{label}}</h3>
        </div>
        <div class="flex mt-2">
          <div class="basis-1/2 text-center">
            <ClockIcon class="inline mr-2" />
            <span class="text-sm">{{time}}</span>
          </div>
          <div class="basis-1/2 items-center">
            <div class="number mr-2">{{ingredients}}</div>
            <span class="text-sm">ингредиентов</span>
          </div>
        </div>
        <div class="flex mt-10 px-10">
          <div class="basis-1/2 text-center">
            <span style="color: #453e43" class="font-semibold">{{views}}</span>
            <EyeIcon class="inline ml-1" />
          </div>
          <div class="basis-1/2 text-center">
            <span style="color: #453e43" class="font-semibold">{{likes}}</span>
            <LikeIcon class="inline ml-1" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

.recipe_wrapper {
  padding: 6px;
}

.recipe {
  cursor: pointer;
  background: var(--lil-light-color);
  border-radius: 40px;
  padding: 22px;
}

.recipe_wrapper:nth-child(2n) .recipe {
  background: var(--green-light-color);
}

.number {
  border: 1px solid #121212;
  width: 20px;
  height: 20px;
  line-height: 1.5;
  //padding-left: 5px;
  border-radius: 20px;
  display: inline-block;
  font-size: 14px;
  text-align: center;
}

</style>