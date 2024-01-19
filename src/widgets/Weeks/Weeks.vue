<script>
import image from "../../assets/images/week-1.png"
export default {
  name: "Weeks",
  data () {
    return {
      image: image,
    }
  }
}
</script>

<template>
  <div class="weeks flex flex-row gap-4 items-center">
    <div class="basis-3/5">
      <img class="w-max" :src="image" alt="Image" />
    </div>
    <div class="weeks_description basis-2/5 flex flex-col gap-4">

      <div class="weeks_block flex items-center p-6 rounded-3xl">
        <div class="text-8xl">8</div>
        <p>из 10 итальянцев едят макаронные изделия каждый день, а на каждого из них приходится 6,5 порций в неделю.</p>
      </div>
      <div class="weeks_block flex items-center p-6 rounded-3xl">
        <div class="text-8xl">350</div>
        <p>различных видов макаронных изделий</p>
      </div>
      <div class="weeks_block flex items-center p-6 rounded-3xl">
        <div class="text-8xl">80</div>
        <p>метров составляет самая длинная паста в мире</p>
      </div>


    </div>
  </div>
</template>

<style scoped>

.weeks_block {
  background: var(--green-light-color);
}

</style>