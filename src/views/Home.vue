<template>
  <div class="home">
 <Newtodo />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"; // @ is an alias to /src
import Newtodo from "@/components/Newtodo.vue";
export default defineComponent({
  name: "Home",
  components: { Newtodo,},
});
</script>
