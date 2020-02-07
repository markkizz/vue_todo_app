<template>
  <div class="container">
    <div class="header"></div>
    <Todos />
  </div>
</template>

<script>
import Todos from './components/Todo';

export default {
  name: 'App',
  components: {
    Todos
  },
  data() {
    return {
      todo: [
        {
          id: 1,
          title: "First Todo",
          isComplete: false
        },
        {
          id: 1,
          title: "First Todo",
          isComplete: false
        }
      ]
    }
  },
}
</script>

<style>
  .container{
    padding:10px;
    width:380px;
    margin:0 auto;
  }
  .header{
    width: 380px;
    height:200px;
    background-image: url('./assets/images.jpg');
    background-size: 100% 100%;
    background-repeat: no-repeat;
    border-radius: 15px 15px 0 0;
    position: relative;
}
.clear{
    width : 30px;
    height: 30px;
    position: absolute;
    right:20px;
    top: 20px;
}
.clear i{
    font-size: 30px;
    color: #FFF;
}
.clear i:hover{
    cursor: pointer;
    text-shadow: 1px 3px 5px #000;
    transform: rotate(45deg);
}
</style>
