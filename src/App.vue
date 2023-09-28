<template>
  <TodoHeader/>
  <RouterView />
</template>

<script setup>
import { RouterLink, RouterView } from "vue-router";
import TodoHeader from "./components/TodoHeader.vue";
</script>
