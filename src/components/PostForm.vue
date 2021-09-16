<template>
  <form @submit.prevent>  <!-- Что бы не перезагружалась страница -->
    <h4>Создание поста</h4>
    <input
        v-bind:value="post.title"
        @input="post.title = $event.target.value"
        class="input"
        type="text"
        placeholder="Название"
    > <!-- v-bind: связывает какие-то данные с каким-то конкретным компонентом.
       Отслеживает изменения в инпуте:
       Вариант 1 : @input="inputTitle" и ниже создаем функцию
       Вариант 2 : @input="title = $event.target.value" и все, но у меня этот вариант не сработал
       Меняем Вариант 1 на Вариант 2 и здесь он сработал
       У меня тормозит то ли phpstorm то ли х.з. бывает клинит-->
    <input
        v-bind:value="post.body"
        @input="post.body = $event.target.value"
        class="input"
        type="text"
        placeholder="Описание"
    >
    <button
        class="btn"
    >
      Создать
    </button> <!-- Создаем слушатель нажатия на кнопку -->
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
  }
}
</script>

<style scoped>
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