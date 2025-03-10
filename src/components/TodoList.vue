<template>
  <li v-for="todo in todos" key="todo.id" class="flex gap-3 my-2">
    <p>{{ todo.text }}</p>
  </li>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps({
  todos: {
    type: Array,
  },
})
</script>
