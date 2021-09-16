<template>
<div class="app">
  <post-form
      @create="createPost"
  /> <!-- Выводим компонент -->
  <post-list
      :posts="posts"
  /> <!-- Выводим компонент, биндим пропсы, более длинная запись такая: v-bind:posts="posts" -->

</div>
</template>

<script>
import PostForm from "./components/PostForm"; // Добавляем компонент
import PostList from "./components/PostList"; // Добавляем компонент
export default {
  components: {
    PostList, PostForm // регистрируем компонент
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'Javascript 1', body: 'Описание поста 1'},
        {id: 1, title: 'Javascript 2', body: 'Описание поста 2'},
        {id: 1, title: 'Javascript 3', body: 'Описание поста 3'},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },

  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}



</style>