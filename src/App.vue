<template>
  <div class="container">
    <div class="header"></div>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" v-on:add-todo="handleAddTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todo";
import axios from 'axios';

export default {
  name: "App",
  components: {
    Todos
  },
  created () {
    axios.get('https://jsonplaceholder.typicode.com/todos/1')
    .then(res => {
      console.log(res.data);
      this.todos = res.data
    })
    .catch(err => console.error(err));
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    handleAddTodo(newTodo) {
      this.todos = [...this.todos, newTodo]
    }
  }
};
</script>

<style>
body {
  padding: 0;
  margin: 0;
  background-color: rgba(0, 0, 0, 0.1);
  font-family: "Titillium Web", sans-serif;
}
.container {
  padding: 10px;
  width: 380px;
  margin: 0 auto;
}
.header {
  width: 380px;
  height: 200px;
  background-image: url("./assets/images.jpg");
  background-size: 100% 100%;
  background-repeat: no-repeat;
  border-radius: 15px 15px 0 0;
  position: relative;
}
.clear {
  width: 30px;
  height: 30px;
  position: absolute;
  right: 20px;
  top: 20px;
}
.clear i {
  font-size: 30px;
  color: #fff;
}
.clear i:hover {
  cursor: pointer;
  text-shadow: 1px 3px 5px #000;
  transform: rotate(45deg);
}
</style>
