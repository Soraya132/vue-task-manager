<script setup>
import { reactive, defineEmits } from "vue";
import TodoButton from "./TodoButton.vue";
const todoState = reactive({
  todo: "",
  invalid: null,
  errMsg: "",
});
const emit = defineEmits(["create-todo"]);
const createTodo = () => {
  if (todoState.todo !== "") {
    emit("create-todo", todoState.todo);
    todoState.todo = "";
    return;
  }
  todoState.invalid = true;
  todoState.errMsg = "Todo value cannot be empty";
  setTimeout(() => {
    todoState.invalid = null;
  }, 2000);
};
</script>
<template>
  <div
    class="my-10 flex border border-gray-300 rounded-sm w-full flex-col sm:flex-row"
    :class="{ 'border-red-500': todoState.invalid }">
    <input
      type="text"
      class="flex-1 py-2 px-1 focus:outline-none text-gray-700 text-xl font-semibold"
      v-model="todoState.todo" />
    <TodoButton @click="createTodo()" />
  </div>
  <p class="text-md font-semibold text-red-500" v-show="todoState.invalid">
    {{ todoState.errMsg }}
  </p>
</template>
