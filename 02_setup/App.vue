<template>
  <h1>{{ number }}</h1>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "App",
  setup() {
    const number = 10;
    return { number };
  }
});
</script>

<style lang="scss"></style>
