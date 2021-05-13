<template>
  <div class="about">
  <HelloWorld2 />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"; // @ is an alias to /src
import HelloWorld2 from "@/components/HelloWorld2.vue";
export default defineComponent({
  name: "HelloWorld2",
  components: {
   HelloWorld2
  },
});
</script>