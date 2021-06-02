<template>
  <div class="home">
    <Todo />
    <Props title="ToDo" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"; // @ is an alias to /src
import Todo from "@/components/Todo.vue";
import Props from "@/components/Props.vue";
export default defineComponent({
  name: "Home",
  components: { Todo, Props },
});
</script>
