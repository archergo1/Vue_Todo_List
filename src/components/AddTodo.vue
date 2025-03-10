<template>
  <form id="form" @submit.prevent="onSubmit">
    <div>
      <input
        v-model="text"
        type="text"
        placeholder="Add a new todo"
        class="border-gray-400 border-[2px] rounded-sm p-4 text-lg"
      />
    </div>
    <div class="mt-2">
      <button class="w-full p-4 text-white bg-blue-500" rounded-sm>Add Todo</button>
    </div>
  </form>
</template>

<script setup>
import { ref, defineEmits } from 'vue'

const text = ref('')

const emit = defineEmits(['addTodo'])

const onSubmit = () => {
  console.log(text.value)

  const todo = {
    id: crypto.randomUUID(),
    text: text.value,
    completed: false,
  }
  emit('addTodo', todo)
}
</script>
