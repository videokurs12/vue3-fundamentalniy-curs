<template>
  <form @submit.prevent>  <!-- Что бы не перезагружалась страница -->
    <h4>Создание поста</h4>
    <my-input
        v-model="post.title"
        type="text"
        placeholder="Название"
    /> <!-- Двухстороннее связывание с использованием диррективы v-model="post.title" -->
    <my-input
        v-model="post.body"
        type="text"
        placeholder="Описание"
    />
    <my-button
        style="align-self: flex-end; margin-top: 15px;"
        @click="createPost"
    >
      Создать
    </my-button> <!-- Создаем слушатель нажатия на кнопку -->
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: '',
      }
    }
  },
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}


</style>