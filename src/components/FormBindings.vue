<script setup>
import { ref } from 'vue'

const text = ref('')
</script>

<template>
  <div class="formbinding-container">
    <div class="formbinding-text">
      <h1><strong>Form Binding</strong></h1>
      <p>
        Form binding di Vue.js adalah mekanisme untuk menghubungkan data dari formulir HTML 
        (seperti input text, textarea, select, checkbox) dengan data dalam instance Vue.js. 
        Ini memungkinkan perubahan pada input langsung memperbarui data, dan sebaliknya, 
        perubahan data juga akan mencerminkan isi input.
      </p>
    </div>

    <div class="formbinding-box">
      <input v-model="text" placeholder="Ketik di sini..." class="input-field" />
      <p class="preview-text">Output: {{ text }}</p>
    </div>
  </div>
</template>

<style scoped>
.formbinding-container {
  display: flex;
  justify-content: space-between;
  gap: 32px;
  background-color: #f8fafc;
  padding: 32px;
  border-radius: 12px;
  margin: 32px;
}

.formbinding-text {
  flex: 2;
  font-size: 1.1em;
  color: #2d3748;
  line-height: 1.6;
}

.formbinding-text h1 {
  font-size: 2em;
  color: #1a202c;
  margin-bottom: 16px;
}

.formbinding-box {
  flex: 1;
  background-color: #fff;
  padding: 24px;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  border: 1px solid #e2e8f0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 16px;
}

.input-field {
  padding: 10px 14px;
  font-size: 1em;
  border-radius: 8px;
  border: 1px solid #cbd5e0;
  outline: none;
  transition: border-color 0.2s ease;
}

.input-field:focus {
  border-color: #3182ce;
}

.preview-text {
  font-size: 1.1em;
  color: #2d3748;
}
</style>
