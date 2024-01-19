<script>
import Button from "../Button/Button.vue";
import Input from "../Input/Input.vue";
import SearchIcon from "../../assets/Icons/SearchIcon/SearchIcon.vue";

export default {
  name: "Search",
  components: {SearchIcon, Input, Button}
}
</script>

<template>
  <div class="search flex p-1 rounded-3xl items-center">
    <SearchIcon class="ml-4" />
    <input class="search_input flex-auto h-8 ml-4 text-base outline-none" placeholder="Найти рецепт" />
    <Button class="flex-none">Найти</Button>
  </div>
</template>

<style scoped>

.search {
  background: var(--blue-light-color);
}

.search_input {
  background: var(--blue-light-color);
}

</style>