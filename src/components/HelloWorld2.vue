<template>
  <div class="wrapper">
    <header>ToDo</header>
    <form class="inputField" @submit.prevent="addNewTodo">
      <input v-model="newTodo" name="newTodo" placeholder="Add todo" />
      <button>Add</button>
    </form>
    <ul>
      <li class="todoList" v-for="(todo, index) in todos" :key="todo.id">
        <h3 :class="{ done: todo.done }" @click="toggleDone(todo)">
          {{ todo.content }}
        </h3>
        <button class="removeTodo" @click="removeTodo(index)">
          Clear Todo
        </button>
      </li>
    </ul>

    <div class="footer">
      <button @click="removeAllTodos">Clear All</button>
      <button @click="markAllDone">All Done</button>
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

.inputField button {
  width: 50px;
  height: 100%;
  border: none;
  color: #fff;
  margin-left: 5px;
  font-size: 21px;
  outline: none;
  background: #87dbd0;
  cursor: pointer;
  border-radius: 3px;
}

.inputField button:hover,
.footer button:hover {
  background: #28e4ab;
}
.inputField button.active {
  opacity: 1;
  pointer-events: auto;
}
.footer button {
  padding: 6px 10px;
  border-radius: 3px;
  border: none;
  outline: none;
  color: #fff;
  font-weight: 400;
  font-size: 16px;
  margin-left: 5px;
  background: #87dbd0;
  cursor: pointer;
}
.footer button.active {
  opacity: 1;
  pointer-events: auto;
}
.wrapper .todo {
  max-height: 250px;
  overflow-y: auto;
}

.done {
  text-decoration: line-through;
}
</style>
