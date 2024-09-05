<template>
  <div>
    <h1>Min seje todo list</h1>
    <div class="add-item">
      <p>Tilføj:</p>
      <input type="text" v-model="newTodo">
      <button v-on:click="addTodo()">Tilføj</button>
    </div>
    <ul>
      <div class="list-item" v-for="(item, index) in todos" :key="index">
        <div class="list-container">
          <input type="checkbox" v-model="item.completed">
          <li :class="{ completed: item.completed }">{{ item.text }}</li>
        </div>
        <button v-on:click="removeTodo(index)">Fjern</button>
      </div>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const todos = ref([])
const newTodo = ref('')

const addTodo = () => {
  if (newTodo.value.trim() !== '') {
    todos.value.push({ text: newTodo.value, completed: false })
    newTodo.value = ''
  }
}

const removeTodo = (index) => {
  todos.value.splice(index, 1)
}

</script>

<style scoped>
.add-item {
  display: flex;
  gap: 1rem;
}
.list-item {
  display: flex;
  justify-content: space-between;
}
.list-container {
  display: flex;
  gap: 1rem;
  list-style: none;
}
</style>
