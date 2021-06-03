<template>
  <div class="about">
  <Todo />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Todo from "@/components/Todo.vue";
export default defineComponent({
  name: "about",
  components: { Todo,},
});
</script>
