<template>
  <div class="add-to-do">
    <font-awesome-icon :icon="['fas', 'plus-circle']" class="add-icon" @click="handleAddTodo" />
    <input type="text" placeholder="Add Todo here" v-model="title">
  </div>
</template>

<script>
import uuid from 'uuid';

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    handleAddTodo() {
      const newTodo = {
        id: uuid.v4(),
        title: this.title,
        isComplete: false
      }
      this.$parent.$emit('add-todo', newTodo)
      this.title = ''
    }
  },
};
</script>

<style scoped>
.add-to-do {
  position: relative;
  top: 0;
  width: 360px;
  height: 40px;
  background-color: #fff;
  padding: 10px;
  border-top: 1px solid rgba(0, 0, 0, 0.1);
}
.add-icon {
  position: absolute;
  font-size: 40px;
  cursor: pointer;
  color: #4162f6;
}

.add-to-do input {
  position: absolute;
  left: 50px;
  height: 35px;
  width: 310px;
  background-color: transparent;
  border: solid #f2f3f5 1px;
  font-size: 20px;
  padding-left: 10px;
}
.add-to-do input::-webkit-input-placeholder {
  /* Chrome/Opera/Safari */
  color: #4162f6;
  font-family: "Titillium Web", sans-serif;
  font-size: 20px;
}
.add-to-do input::-moz-placeholder {
  /* Firefox 19+ */
  color: #4162f6;
  font-family: "Titillium Web", sans-serif;
  font-size: 20px;
}
.add-to-do input:-ms-input-placeholder {
  /* IE 10+ */
  color: #4162f6;
  font-family: "Titillium Web", sans-serif;
  font-size: 20px;
}
.add-to-do input:-moz-placeholder {
  /* Firefox 18- */
  color: #4162f6;
  font-family: "Titillium Web", sans-serif;
  font-size: 20px;
}
</style>
