<template>git commit -m "Add placeholder"
<div class="wrapper">
<header>Tasks</header>
<div class="inputField">
<input type="text" placeholder="Add task">
</div>
</div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HelloWorld",
  props: {
  
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

header{
font-weight: bold;
color:#2c3e50;
font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
