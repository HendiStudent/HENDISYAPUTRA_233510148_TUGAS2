<script setup>
import { ref } from 'vue'

const awesome = ref(true)

function toggle() {
  awesome.value = !awesome.value
}
</script>

<template>
  <div class="conditional-container">
    <div class="conditional-text">
      <h1><strong>Conditional Rendering</strong></h1>
      <p>
        Conditional rendering di Vue.js adalah kemampuan untuk menentukan bagian dari template HTML 
        yang akan dirender berdasarkan kondisi tertentu. Ini memungkinkan Anda untuk memunculkan atau menyembunyikan 
        bagian-bagian UI berdasarkan data atau logika tertentu, membuat aplikasi lebih dinamis dan responsif.
      </p>
    </div>

    <div class="conditional-box">
      <button @click="toggle" class="toggle-button">Toggle</button>
      <h2 v-if="awesome" class="yes-text">Vue is awesome! 🎉</h2>
      <h2 v-else class="no-text">Oh no 😢</h2>
    </div>
  </div>
</template>

<style scoped>
.conditional-container {
  display: flex;
  justify-content: space-between;
  gap: 32px;
  background-color: #f8fafc;
  padding: 32px;
  border-radius: 12px;
  margin: 32px;
}

.conditional-text {
  flex: 2;
  font-size: 1.1em;
  color: #2d3748;
  line-height: 1.6;
}

.conditional-text h1 {
  font-size: 2em;
  color: #1a202c;
  margin-bottom: 16px;
}

.conditional-box {
  flex: 1;
  background-color: #fff;
  padding: 24px;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  border: 1px solid #e2e8f0;
  text-align: center;
}

.toggle-button {
  background-color: #3182ce;
  color: white;
  padding: 10px 16px;
  border: none;
  border-radius: 8px;
  font-size: 1em;
  margin-bottom: 16px;
  cursor: pointer;
}

.yes-text {
  color: #2f855a;
  font-size: 1.5em;
}

.no-text {
  color: #e53e3e;
  font-size: 1.5em;
}
</style>
