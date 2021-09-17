<template>
  <div>
    <h3>Список постов</h3>
    <post-item
        v-for="post in posts"
        :post="post"
    />
  </div>
</template>

<script>
import PostItem from "./PostItem";
export default {
  components: {PostItem},
  props: {
    posts: { // Пропсы. В дочернем компоненте изменять нельзя
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

</style>