<template>
<div>
  <button v-on:click="addLike">likes</button> <!-- v-on:click= слушатель события -->
  <button @click="addDislike">Dislikes</button> <!-- v-on:click= слушатель события, новый синтаксис -->
  <div>Кол-во лайков: <strong>{{ likes }}</strong></div>
  <div>Кол-во дизлайков: <strong>{{ dislikes }}</strong></div>
</div>
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
      dislikes: 0,
    }
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislikes +=1;
    }
  }
}
</script>

<style scoped>

</style>