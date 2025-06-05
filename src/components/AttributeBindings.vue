<script setup>
import { ref } from 'vue'

const titleClass = ref('title')
</script>

<template>
  <div class="attribute-container">
    <div class="attribute-text">
      <h1><strong>Attribute Bindings</strong></h1>
      <p>
        Atribut binding adalah mekanisme untuk mengikat nilai data pada atribut HTML atau properti DOM, 
        sehingga perubahan pada data secara otomatis akan memengaruhi tampilan. 
        Dalam konteks pemrograman web, ini memungkinkan interaksi yang dinamis antara templat dan data.
      </p>
    </div>

    <div class="attribute-box">
      <h2 :class="titleClass">Make me red</h2>
    </div>
  </div>
</template>

<style scoped>
.attribute-container {
  display: flex;
  justify-content: space-between;
  gap: 32px;
  background-color: #f8fafc;
  padding: 32px;
  border-radius: 12px;
  margin: 32px;
}

.attribute-text {
  flex: 2;
  font-size: 1.1em;
  color: #2d3748;
  line-height: 1.6;
}

.attribute-text h1 {
  font-size: 2em;
  color: #1a202c;
  margin-bottom: 16px;
}

.attribute-box {
  flex: 1;
  background-color: #fff;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  border: 1px solid #e2e8f0;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.title {
  color: red;
  font-size: 1.5em;
}
</style>
