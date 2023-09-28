<script setup>
import { Icon } from "@iconify/vue";
const props = defineProps({
  todo: {
    type: Object,
    required: true,
  },
  index: {
    type: Number,
    required: true,
  },
});
defineEmits(["toggle-completed", "emit-todo", "update-todo", "delete-todo"]);
</script>
<template>
  <li
    class="flex items-center gap-3 py-5 px-4 w-full border-b border-gray-200 bg-gray-200 shadow-lg mb-3 flex-wrap">
    <div class="flex items-center gap-4 flex-1">
      <input
        type="checkbox"
        :checked="todo.isCompleted"
        @input="$emit('toggle-completed', index)"
        class="flex-1 py-2 px-1 focus:outline-none cursor-pointer text-gray-700 text-xl font-semibold" />
      <div class="flex flex-col gap-2 w-full">
        <input
          v-if="todo.isEditing"
          type="text"
          :value="todo.todo"
          @input="$emit('update-todo', $event.target.value, index)"
          class="py-1 px-2 border border-gray-200 focus:outline-none rounded-md" />
        <span
          v-else
          class="text-gray-500"
          :class="{ 'line-through': todo.isCompleted }"
          >{{ todo.todo }}</span
        >
      </div>
    </div>
    <div class="flex items-center gap-2 justify-end">
      <Icon
        v-if="todo.isEditing"
        icon="ph:check-circle"
        color="#41b080"
        width="22"
        class="cursor-pointer"
        @click="$emit('emit-todo', index)" />
      <Icon
        v-else
        icon="ph:pencil-fill"
        color="#41b080"
        width="22"
        class="cursor-pointer"
        @click="$emit('emit-todo', index)" />
      <Icon
        icon="ph:trash"
        color="#f95e5e"
        width="22"
        class="cursor-pointer"
        @click="$emit('delete-todo', todo.id)" />
    </div>
  </li>
</template>
