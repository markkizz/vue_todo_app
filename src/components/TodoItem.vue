<template>
  <li class="item">
    <!-- complete sec -->
    <div @click="clickComplete">
      <font-awesome-icon :icon="['far', 'circle']" class="isComplete-icon" v-if="todo.isComplete===false"/>
      <font-awesome-icon :icon="['fa', 'check-circle']" class="isComplete-icon" v-else />
    </div>
    <p class="text" v-bind:class="{'lineThrough':todo.isComplete}">{{todo.title}}</p>
    <!-- trash sec -->
    <font-awesome-icon :icon="['far', 'trash-alt']" class="trash-icon" @click="$emit('del-todo', todo.id)" />
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    clickComplete() {
      this.todo.isComplete = !this.todo.isComplete
    }
  }
};
</script>

<style scoped>
.item {
  width: 380px;
  height: 45px;
  min-height: 45px;
  position: relative;
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  list-style: none;
  padding: 0;
  margin: 0;
}

.isComplete-icon {
  position: absolute;
  font-size: 20px;
  padding-left: 5px;
  left: 15px;
  top: 12px;
}

.isComplete-icon:hover {
  cursor: pointer;
}

.fa-check-circle {
  color: #6eb200;
}

.item p.text {
  position: absolute;
  padding: 0;
  margin: 0;
  font-size: 20px;
  left: 55px;
  top: 5px;
  background-color: #fff;
  max-width: 285px;
}

.lineThrough {
  text-decoration: line-through;
  color: #ccc;
}

.trash-icon {
  position: absolute;
  font-size: 25px;
  right: 15px;
  top: 10px;
}

.trash-icon:hover {
  color: #af0000;
  cursor: pointer;
}
</style>
