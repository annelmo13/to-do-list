<template>
<v-container>
<v-layout align-center justify-center>
 <v-form>
   <label>New ToDo</label>
  <input v-model="newTodo" name="newTodo" placeholder="Add todo">
   <button>Add</button>
 </v-form>
 </v-layout>
 </v-container>
</template>
<script lang="ts">
export default {};
</script>
<style scoped>
body {
  font-family: sans-serif;
  padding-top: 1em;
  padding-bottom: 1em;
  font-size: 2em;
  width: 80%;
  margin: 0 auto;
}
input, textarea, button {
  display: 'block';
  width: 100%;
  font-family: sans-serif;
  font-size: 1em;
  margin: 0.5em;
}
.todo {
  cursor: pointer;
}
.done {
  text-decoration: line-through;
}
</style>