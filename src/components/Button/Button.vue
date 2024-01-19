<script>
export default {
  name: "Button",
  props: {
    styles: {
      type: String,
      required: true,
    }
  }
}
</script>

<template>
  <button :class="styles"><slot></slot></button>
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
  display: inline-block;
  background: var(--green-light-color);
  color: #1a1a1a;
  font-weight: 500;
  padding: 10px 100px;
  outline: none;
  border-radius: 50px;
  border: 1px solid var(--green-light-color);
}
.green:hover {
  border: 1px solid #1a1a1a;
}
.green:focus {
  border: 1px solid var(--lil-light-color);
  background: var(--lil-light-color);
}
</style>