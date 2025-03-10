<script setup>
import AddTodo from './components/AddTodo.vue'
import TodoList from './components/TodoList.vue'
import { ref } from 'vue'
// like useState in React
const todos = ref([
  {
    id: 1,
    text: 'COOK',
  },
])

const handleAddTodo = (todo) => {
  console.log('handleAddTodo', todo)
  todos.value.push(todo)
}
</script>

<template>
  <div>
    <AddTodo @add-todo="handleAddTodo" />
    <TodoList :todos="todos" />
  </div>
</template>
