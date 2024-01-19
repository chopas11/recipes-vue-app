<script>
import Input from "../../components/Input/Input.vue";
import Logo from "../../components/Logo/Logo.vue";
import Search from "../../components/Search/Search.vue";

export default {
  name: "Header",
  components: {Search, Logo, Input},
  // components: {LinkerListItem},
  // data() {
  //   return {
  //
  //   }
  // }
}
</script>

<template>
  <div class="header flex flex-row items-center my-5">
    <div class="header_logo basis-1/4">
      <Logo />
    </div>
    <div class="header_search basis-3/4">
      <Search />
    </div>
  </div>
</template>

<style scoped>

</style>