<template>
  <div class="about">
  <Todo />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"; // @ is an alias to /src
import Todo from "@/components/Todo.vue";
export default defineComponent({
  name: "Todo",
  components: {
   Todo, 
  },
});
</script>
