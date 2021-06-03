<template>
  <div class="wrapper">
    <header>ToDo</header>

    <form class="inputField" @submit.prevent="addNewTodo">
      <input v-model="newTodo" name="newTodo" autocomplete="off">
      <v-btn color="secondary">Add</v-btn>
    </form>
    <ul>
      <li class="todoList" v-for="(todo, index) in todos" :key="todo.id">
        <h3 :class="{ done: todo.done }" @click="toggleDone(todo)">
          {{ todo.content }}
        </h3>
        <v-btn color="secondary" @click="removeTodo(index)">Clear Todo</v-btn>
      </li>
    </ul>

    <div class="footer">
      <v-btn color="secondary" @click="removeAllTodos">Clear All</v-btn>
      <v-btn color="secondary" @click="markAllDone">All Done</v-btn>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const newTodo = ref("");
    const todos = ref([]);
    function addNewTodo() {
      todos.value.push({
        id: Date.now(),
        done: false,
        content: newTodo.value,
      });
      newTodo.value = "";
    }
    function toggleDone(todo) {
      todo.done = !todo.done;
    }
    function removeTodo(index) {
      todos.value.splice(index, 1);
    }
    function markAllDone() {
      todos.value.forEach(todo => (todo.done = true));
    }
    function removeAllTodos() {
      todos.value = [];
    }
    return {
      todos,
      newTodo,
      addNewTodo,
      toggleDone,
      removeTodo,
      markAllDone,
      removeAllTodos,
    };
  },
};
</script>

<style>
body {
  width: 100%;
  height: 100vh;
  padding: 10px;
}
.wrapper {
  background: #fff;
  max-width: 400px;
  width: 100%;
  margin: 120px auto;
  padding: 25px;
  border-radius: 5px;
  box-shadow: 0px 10px 15px rgba(0, 0, 0, 0.1);
}
.wrapper header {
  font-size: 20px;
  font-weight: bold;
  color: #2c3e50;
  font-family: Arial, Helvetica, sans-serif;
}
.wrapper .inputField {
  margin: 20px 0;
  width: 100%;
  display: flex;
  height: 45px;
}
.inputField input {
  width: 85%;
  height: 100%;
  outline: none;
  border-radius: 3px;
  border: 1px solid #ccc;
  font-size: 17px;
  padding-left: 15px;
  transition: all 0.3s ease;
}
.inputField input:focus {
  border-color: #2c3e50;
}
.wrapper .todo {
  max-height: 250px;
  overflow-y: auto;
}
.done {
  text-decoration: line-through;
}
</style>