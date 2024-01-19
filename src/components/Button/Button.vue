<script>
export default {
  name: "Button"
}
</script>

<template>
  <button class="white"><slot></slot></button>
</template>

<style scoped>

.white {
  display: block;
  background: white;
  color: #1a1a1a;
  font-weight: 500;
  padding: 6px 20px;
  outline: none;
  border-radius: 50px;
}

.white:hover {
  color: var(--lil-light-color);
}

.white:focus {
  background: var(--green-light-color);
  color: #1a1a1a;

}

.green {

}

</style>