<script setup>
import TodoCreator from "../components/TodoCreator.vue";
import TodoItem from "../components/TodoItem.vue";
import { Icon } from "@iconify/vue";
import { uid } from "uid";
import { ref, watch, computed } from "vue";

const todoList = ref([]);
watch(
  todoList,
  () => {
    setTodoListLocalStorage();
  },
  { deep: true }
);
const createTodo = (todo) => {
  todoList.value.push({
    id: uid(),
    todo,
    isCompleted: false,
    isEditing: null,
  });
};

const fetchTodoList = () => {
  const savedTodoList = JSON.parse(localStorage.getItem("todoList"));
  if (savedTodoList) {
    todoList.value = savedTodoList;
  }
};
fetchTodoList();
const setTodoListLocalStorage = () => {
  localStorage.setItem("todoList", JSON.stringify(todoList.value));
};
const toggleTodoComplete = (todoPos) => {
  todoList.value[todoPos].isCompleted = !todoList.value[todoPos].isCompleted;
};
const toggleEditTodo = (todoPos) => {
  todoList.value[todoPos].isEditing = !todoList.value[todoPos].isEditing;
};
const updateTodo = (value, todoPos) => {
  todoList.value[todoPos].todo = value;
};
const deleteTodo = (todoId) => {
  todoList.value = todoList.value.filter((todo) => todo.id != todoId);
};
const todoCompleted = computed(() => {
  return todoList.value.every((todo) => todo.isCompleted);
});
</script>
<template>
  <div class="mx-auto w-full lg:w-[70%] px-4 mb-20">
    <div class="flex items-center flex-col pt-16">
      <h1 class="text-6xl font-bold text-gray-700 text-center">Create Todo</h1>
      <TodoCreator @create-todo="createTodo" />
    </div>
    <ul v-if="todoList.length > 0" class="flex items-center flex-col">
      <TodoItem
        v-for="(todo, index) in todoList"
        :todo="todo"
        :index="index"
        :key="todo.id"
        @toggle-completed="toggleTodoComplete"
        @emit-todo="toggleEditTodo"
        @update-todo="updateTodo"
        @delete-todo="deleteTodo" />
    </ul>
    <div v-else class="flex gap-2 items-center justify-center">
      <Icon icon="noto-v1:sad-but-relieved-face" width="22" />
      <span class="text-lg font-semibold text-gray-500">
        you have no todo's to complete! add one!</span
      >
    </div>
    <div
      v-if="todoCompleted && todoList.length > 0"
      class="flex gap-2 items-center justify-center">
      <Icon icon="noto-v1:party-popper" />
      <span class="text-lg font-semibold text-gray-500"
        >you have completed all of your todo's</span
      >
    </div>
  </div>
</template>
