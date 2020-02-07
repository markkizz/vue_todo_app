<template>
  <div>
    <div class="content">
      <ul class="list" v-for="todo in todos" :key="todo.id">
        <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
      </ul>
    </div>
    <AddTodo />
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
import AddTodo from "./AddTodo";

export default {
  name: "Todos",
  components: {
    TodoItem,
    AddTodo
  },
  props: ["todos"],
  methods: {
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
