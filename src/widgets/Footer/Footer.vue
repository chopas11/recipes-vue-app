<script>
import { Icon } from '@iconify/vue';
import Logo from "../../components/Logo/Logo.vue";

export default {
  name: "Footer",
  components: {Logo, Icon}
}
</script>

<template>
  <div class="footer container mx-auto flex flex-row justify-between items-center">
    <div>
      <Logo />
    </div>
    <div class="flex">
      <Icon icon="lets-icons:insta" width="24" height="24" />
      <Icon icon="ri:vk-line" width="24" height="24" />
    </div>
    <div>
      <p class="text-medium">tut1@gmail.com</p>
    </div>
  </div>
</template>

<style scoped>
  .footer {
    height: 60px;
    //margin-top: -90px;
  }
</style>