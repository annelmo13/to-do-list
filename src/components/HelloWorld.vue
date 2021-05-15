<template>
<div class="wrapper">
<header>Tasks</header>
<div class="inputField">
<input type="text" placeholder="Add task">
<button><font-awesome-icon :icon="['fas', 'faPlus']" /></button>
</div>
<ul class="todoList">
</ul>
</div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "HelloWorld",
  props: {
  
  },
});

import { library } from '@fortawesome/fontawesome-svg-core'

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.wrapper{
  background: #fff;
  max-width: 400px;
  width: 100%;
  margin: 120px auto;
  padding: 25px;
  border-radius: 5px;
  box-shadow: 0px 10px 15px rgba(0,0,0,0.1);
}
.wrapper header{
 font-size: 20px;
 font-weight: bold;
 color:#2c3e50;
 font-family: Arial, Helvetica, sans-serif;
}
.wrapper .inputField{
  margin: 20px 0;
  width: 100%;
  display: flex;
  height: 45px;
}
.inputField input{
  width: 85%;
  height: 100%;
  outline: none;
  border-radius: 3px;
  border: 1px solid #ccc;
  font-size: 17px;
  padding-left: 15px;
  transition: all 0.3s ease;
}
.inputField input:focus{
  border-color: #2c3e50;;
}

.inputField button{
  width: 50px;
  height: 100%;
  border: none;
  color:honeydew;
  margin-left: 10px;
  cursor: pointer;
  border-radius: 3px;
  pointer-events: none;
}

</style>
