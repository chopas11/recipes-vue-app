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
  // },
  methods: {
    updateSearchInput (query) {
      this.$emit('search', query);
    }
  }
}
</script>

<template>
  <div class="header flex flex-row items-center py-5">
    <div class="header_logo basis-1/4">
      <Logo />
    </div>
    <div class="header_search basis-3/4">
<!--      <input @change="updateSearchInput" placeholder="" />-->
      <Search @search="updateSearchInput" @show="this.$emit('show')" />
    </div>
  </div>
</template>

<style scoped>

</style>