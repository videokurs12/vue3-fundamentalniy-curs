<template>
  <button class="btn">
    <slot></slot>  <!-- Что бы вывести надпись на кнопке -->
  </button>

</template>

<script>
export default {
  name: "my-button"
}
</script>

<style scoped>

.btn {
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

</style>