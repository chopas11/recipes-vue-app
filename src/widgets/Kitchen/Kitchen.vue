<script>
import StarIcon from "../../assets/Icons/StarIcon/StarIcon.vue";

export default {
  name: "Kitchen",
  components: {StarIcon},
  props: {
    label: {
      type: String,
      required: true,
    },
    dishes: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    }
  }
}
</script>

<template>
  <div class="kitchen flex flex-row gap-3 mt-10">
    <div class="basis-2/5">
      <div :class="color" class="p-6 rounded-3xl text-3xl font-semibold">{{label}}</div>
    </div>

    <div class="basis-3/5 flex flex-col gap-3">
      <div :class="color" class="p-6 rounded-3xl"><p v-html="description"></p></div>
      <div :class="color" class="p-6 rounded-3xl">
        <h3>Популярные блюда <StarIcon class="inline" /></h3>
        <p>{{dishes}}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>