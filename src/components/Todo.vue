<template>
  <div class="content">
    <ul class="list">
      <TodoItem />
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem';

export default {
  name: "Todos",
  components: {
    TodoItem
  }
};

</script>

<style scoped>
.content {
  width: 380px;
  height: 350px;
  max-height: 350px;
  background-color: #fff;
  overflow: auto;
}
.content::-webkit-scrollbar {
  display: none;
}
.content ul {
  padding: 0;
  margin: 0;
}

</style>
