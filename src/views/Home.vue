<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
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
    HelloWorld, HelloWorld2
  },
});
</script>
