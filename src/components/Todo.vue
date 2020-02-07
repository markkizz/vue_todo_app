<template>
  <div class="content">
    <ul class="list">
      <li class="item">
        <i class="fa ${ic} co" onclick="" isComplete></i>
        <p class="text"></p>
        <i class="fa fa-trash-o de" onclick></i>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Todos"
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
.item i.co {
  position: absolute;
  font-size: 25px;
  padding-left: 5px;
  left: 15px;
  top: 10px;
}
.item i.co:hover {
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
  left: 50px;
  top: 5px;
  background-color: #fff;
  max-width: 285px;
}
.lineThrough {
  text-decoration: line-through;
  color: #ccc;
}
.item i.de {
  position: absolute;
  font-size: 25px;
  right: 15px;
  top: 10px;
}
.item i.de:hover {
  color: #af0000;
  cursor: pointer;
}
</style>
