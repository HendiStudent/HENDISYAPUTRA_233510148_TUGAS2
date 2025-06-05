<script setup>
import { ref, computed } from 'vue'

let id = 0

const newTodo = ref('')
const hideCompleted = ref(false)

const todos = ref([
  { id: id++, text: 'Learn HTML', done: true },
  { id: id++, text: 'Learn JavaScript', done: true },
  { id: id++, text: 'Learn Vue', done: false }
])

const filteredTodos = computed(() => {
  return hideCompleted.value
    ? todos.value.filter((t) => !t.done)
    : todos.value
})

function addTodo() {
  if (newTodo.value.trim()) {
    todos.value.push({ id: id++, text: newTodo.value.trim(), done: false })
    newTodo.value = ''
  }
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}
</script>

<template>
  <div class="computed-container">
    <div class="computed-text">
      <h1><strong>Computed Properties</strong></h1>
      <p>
        Computed properties di Vue.js adalah fungsi yang menghitung nilai berdasarkan data reaktif. Nilai ini otomatis diperbarui ketika
        dependensinya berubah. Berbeda dengan method, computed akan di-cache sehingga hanya dihitung ulang saat data terkait berubah, 
        membuatnya efisien untuk logika turunan dari state.
      </p>
    </div>

    <div class="computed-box">
      <form @submit.prevent="addTodo" class="todo-form">
        <input v-model="newTodo" required placeholder="Tambah todo baru" class="todo-input" />
        <button class="add-btn">Tambah</button>
      </form>

      <ul class="todo-list">
        <li v-for="todo in filteredTodos" :key="todo.id" class="todo-item">
          <label>
            <input type="checkbox" v-model="todo.done" />
            <span :class="{ done: todo.done }">{{ todo.text }}</span>
          </label>
          <button @click="removeTodo(todo)" class="delete-btn">×</button>
        </li>
      </ul>

      <button @click="hideCompleted = !hideCompleted" class="toggle-btn">
        {{ hideCompleted ? 'Tampilkan semua' : 'Sembunyikan yang selesai' }}
      </button>
    </div>
  </div>
</template>

<style scoped>
.computed-container {
  display: flex;
  justify-content: space-between;
  gap: 32px;
  background-color: #f8fafc;
  padding: 32px;
  border-radius: 12px;
  margin: 32px;
}

.computed-text {
  flex: 2;
  font-size: 1.1em;
  color: #2d3748;
  line-height: 1.6;
}

.computed-text h1 {
  font-size: 2em;
  color: #1a202c;
  margin-bottom: 16px;
}

.computed-box {
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

.done {
  text-decoration: line-through;
  color: #718096;
}

.delete-btn {
  background-color: transparent;
  border: none;
  color: #e53e3e;
  font-size: 1.2em;
  cursor: pointer;
}

.toggle-btn {
  margin-top: 12px;
  background-color: #4a5568;
  color: #fff;
  padding: 8px 16px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
}
</style>
