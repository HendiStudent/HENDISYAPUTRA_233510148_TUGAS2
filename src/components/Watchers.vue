<script setup>
import { ref, watch } from 'vue'

const todoId = ref(1)
const todoData = ref(null)

async function fetchData() {
  todoData.value = null
  const res = await fetch(
    `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
  )
  todoData.value = await res.json()
}

fetchData()
watch(todoId, fetchData)
</script>

<template>
  <div class="watcher-container">
   
    <div class="watcher-text">
      <h1><strong>Watchers di Vue.js</strong></h1>
      <p>
        <strong>Watchers</strong> atau pengawas dalam Vue.js adalah mekanisme untuk memantau perubahan pada data reaktif 
        dan menjalankan fungsi tertentu sebagai respons. Ini sangat berguna untuk merespons perubahan data secara asinkron, 
        seperti melakukan permintaan data ke API saat nilai berubah.
      </p>
    </div>

   
    <div class="watcher-demo">
      <p><strong>Todo ID:</strong> {{ todoId }}</p>
      <button @click="todoId++" :disabled="!todoData" class="btn">
        Fetch Next Todo
      </button>
      <p v-if="!todoData" class="loading">Loading...</p>
      <pre v-else class="result">{{ todoData }}</pre>
    </div>
  </div>
</template>

<style scoped>
.watcher-container {
  display: flex;
  flex-direction: row;
  gap: 32px;
  background-color: #f8fafc;
  padding: 32px;
  border-radius: 12px;
  margin: 32px auto;
  max-width: 900px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
}

.watcher-text {
  flex: 2;
  font-size: 1.1em;
  color: #2d3748;
  line-height: 1.6;
}

.watcher-text h1 {
  font-size: 2em;
  color: #1a202c;
  margin-bottom: 16px;
}

.watcher-demo {
  flex: 1.2;
  background-color: #fff;
  padding: 24px;
  border-radius: 12px;
  border: 1px solid #e2e8f0;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.04);
}

.btn {
  background-color: #3182ce;
  color: white;
  border: none;
  padding: 10px 16px;
  font-size: 1em;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s ease;
  margin: 16px 0;
}

.btn:disabled {
  background-color: #a0aec0;
  cursor: not-allowed;
}

.btn:hover:enabled {
  background-color: #2b6cb0;
}

.loading {
  font-style: italic;
  color: #718096;
  margin-bottom: 12px;
}

.result {
  background-color: #f1f5f9;
  padding: 12px;
  border-radius: 8px;
  font-family: monospace;
  font-size: 0.95em;
  white-space: pre-wrap;
  color: #2d3748;
}
</style>
