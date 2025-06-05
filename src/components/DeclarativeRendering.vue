<script setup>
import { reactive, ref } from 'vue'

const message1 = ref(
  'Rendering deklaratif adalah proses di mana aplikasi menggambarkan apa yang ingin ditampilkan di antarmuka pengguna, dan kerangka kerja atau sistem yang digunakan mengurus detail bagaimana tampilan tersebut dirender. Dengan kata lain, programmer fokus pada mendefinisikan state akhir (apa yang ingin dilihat) dan membiarkan sistem menangani bagaimana tampilan berubah untuk mencapai state tersebut.'
)
const counter = reactive({ count: 0 })
const message = ref('Hello World!')
</script>

<template>
  <div class="declarative-container">
    <div class="declarative-text">
      <h1><strong>Declarative Rendering</strong></h1>
      <p>{{ message1 }}</p>
    </div>

    <div class="declarative-box">
      <h2>{{ message }}</h2>
      <p><strong>Count is:</strong> {{ counter.count }}</p>
    </div>
  </div>
</template>

<style scoped>
.declarative-container {
  display: flex;
  justify-content: space-between;
  gap: 32px;
  background-color: #f8fafc;
  padding: 32px;
  border-radius: 12px;
  margin: 32px;
}

.declarative-text {
  flex: 2;
  font-size: 1.1em;
  color: #2d3748;
  line-height: 1.6;
}

.declarative-text h1 {
  font-size: 2em;
  color: #1a202c;
  margin-bottom: 16px;
}

.declarative-box {
  flex: 1;
  background-color: #fff;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  border: 1px solid #e2e8f0;
  text-align: center;
}

.declarative-box h2 {
  font-size: 1.5em;
  color: #2c5282;
  margin-bottom: 12px;
}

.declarative-box p {
  font-size: 1.1em;
  color: #4a5568;
}
</style>
