<template>
<div class="app">
  <form @submit.prevent>  <!-- Что бы не перезагружалась страница -->
    <h4>Создание поста</h4>
    <input
        v-bind:value="title"
        @input="inputTitle"
        class="input"
        type="text"
        placeholder="Название"
    > <!-- v-bind: связывает какие-то данные с каким-то конкретным компонентом.
       Отслеживает изменения в инпуте:
       Вариант 1 : @input="inputTitle" и ниже создаем функцию
       Вариант 2 : @input="title = $event.target.value" и все, но у меня этот вариант не сработал-->
    <input
        v-bind:value="body"
        @input="inputBody"
        class="input"
        type="text"
        placeholder="Описание"
    >
    <button
        class="btn"
        @click="createPost"
    >
      Создать
    </button> <!-- Создаем слушатель нажатия на кнопку -->
  </form>
  <div class="post" v-for="post in posts">
    <div><strong>Название:</strong> {{ post.title }}</div>
    <div><strong>Описание:</strong> {{ post.body }}</div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'Javascript 1', body: 'Описание поста 1'},
        {id: 1, title: 'Javascript 2', body: 'Описание поста 2'},
        {id: 1, title: 'Javascript 3', body: 'Описание поста 3'},
      ],
      title: '',
      body: '',
    }
  },
  methods: {
    createPost(event) {
      const newPost = { // Добавляем новую запись
        id: Date.now(),
        title: this.title,
        body: this.body,
      }
      this.posts.push(newPost);
      this.title = ''; // очищаем данные в инпуте после добавления
      this.body = ''; // очищаем данные в инпуте после добавления
    },
    inputTitle(event) {
      this.title = event.target.value; // <!-- Помещаем данные из инпута в переменную -->
    },
    inputBody(event) {
      this.body = event.target.value; // <!-- Помещаем данные из инпута в переменную -->
    }
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

.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}



</style>