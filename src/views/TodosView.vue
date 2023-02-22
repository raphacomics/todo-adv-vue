<script setup>
import { ref } from 'vue';
import { uid } from 'uid'
import TodoCreator from '../components/TodoCreator.vue';

const todoList = ref([])



const createTodo = (todo) => {
  todoList.value.push({
    id: uid(),
    todo,
    isComplete: null,
    isEditing: null
  })
}
</script>

<template>
  <main class="container text-center my-4">
    <h2 class="fw-bold">Create Todo</h2>
    <TodoCreator @create-todo="createTodo()" />
  </main>
</template>
