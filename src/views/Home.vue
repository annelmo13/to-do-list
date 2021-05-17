<template>
  <div class="home">
    <HelloWorld />
    <HelloWorld2 />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import HelloWorld2 from "@/components/HelloWorld2.vue";
export default defineComponent({
  name: "Home",
  components: {
    HelloWorld, HelloWorld2, 
  },
});
</script>
