<script setup>
import { ref } from 'vue'

let id = 0

const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'Learn HTML' },
  { id: id++, text: 'Learn JavaScript' },
  { id: id++, text: 'Learn Vue' }
])


function addTodo() {
  if (newTodo.value.trim()) {
    todos.value.push({ id: id++, text: newTodo.value.trim() })
    newTodo.value = ''
  }
}


function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}
</script>

<template>
  <div class="list-container">
  
    <div class="list-text">
      <h1><strong>List Rendering</strong></h1>
      <p>
        List rendering (perenderan daftar) dalam Vue.js adalah kemampuan untuk menampilkan data secara dinamis dari sebuah array 
        atau daftar. Ini memungkinkan Anda untuk merender konten yang sama berulang kali, dengan setiap iterasi menggunakan data 
        yang berbeda dari daftar tersebut. Proses ini biasanya menggunakan direktif <code>v-for</code> di Vue.js.
      </p>
    </div>

    
    <div class="list-box">
      <form @submit.prevent="addTodo" class="todo-form">
        <input
          v-model="newTodo"
          required
          placeholder="Tambahkan todo baru"
          class="todo-input"
        />
        <button class="add-btn">Add</button>
      </form>
      <ul class="todo-list">
        <li v-for="todo in todos" :key="todo.id" class="todo-item">
          {{ todo.text }}
          <button @click="removeTodo(todo)" class="delete-btn">×</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.list-container {
  display: flex;
  justify-content: space-between;
  gap: 32px;
  background-color: #f8fafc;
  padding: 32px;
  border-radius: 12px;
  margin: 32px;
}

.list-text {
  flex: 2;
  font-size: 1.1em;
  color: #2d3748;
  line-height: 1.6;
}

.list-text h1 {
  font-size: 2em;
  color: #1a202c;
  margin-bottom: 16px;
}

.list-box {
  flex: 1;
  background-color: #fff;
  padding: 24px;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  border: 1px solid #e2e8f0;
}

.todo-form {
  display: flex;
  gap: 8px;
  margin-bottom: 16px;
}

.todo-input {
  flex: 1;
  padding: 10px;
  border: 1px solid #cbd5e0;
  border-radius: 8px;
  font-size: 1em;
}

.add-btn {
  background-color: #3182ce;
  color: white;
  border: none;
  padding: 10px 16px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
}

.todo-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #edf2f7;
  padding: 8px 12px;
  border-radius: 8px;
  margin-bottom: 8px;
}

.delete-btn {
  background-color: transparent;
  border: none;
  color: #e53e3e;
  font-size: 1.2em;
  cursor: pointer;
}
</style>
