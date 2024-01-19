<script>
export default {
  name: "Input",
  props: {
    // value: {
    //   type: String,
    // },
    placeholder: {
      type: String,
      required: true,
    },
  }
}
</script>

<template>
  <input class="input" type="text" value="" placeholder="Найти рецепт" >
</template>

<style scoped>

</style>