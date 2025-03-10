<script setup>
import AddTodo from './components/AddTodo.vue'
import TodoList from './components/TodoList.vue'
import { ref } from 'vue'
// like useState in React
const todos = ref([
  {
    id: 1,
    text: 'COOK',
    completed: false,
  },
])

const handleAddTodo = (todo) => {
  console.log('handleAddTodo', todo)
  if (todo.text === '') {
    alert('Please enter a todo')
    return
  }
  todos.value.push(todo)
}

const handleDeleteTodo = (todoId) => {
  todos.value = todos.value.filter((todo) => todo.id !== todoId)
}

const handleCompleteTodo = (todoId) => {
  todos.value = todos.value.map((todo) =>
    todo.id === todoId ? { ...todo, completed: !todo.completed } : todo,
  )
}
</script>

<template>
  <div>
    <AddTodo @add-todo="handleAddTodo" />
    <TodoList :todos="todos" @delete-todo="handleDeleteTodo" @complete-todo="handleCompleteTodo" />
  </div>
</template>
