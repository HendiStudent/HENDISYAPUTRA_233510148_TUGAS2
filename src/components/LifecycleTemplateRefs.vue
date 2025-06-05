<script setup>
import { ref, onMounted } from 'vue'

const pElementRef = ref(null)

onMounted(() => {
  pElementRef.value.textContent = 'Komponen telah dimount!'
})
</script>

<template>
  <div class="lifecycle-container">
    <div class="lifecycle-text">
      <h1><strong>Lifecycle Hooks</strong></h1>
      <p>
        Lifecycle hooks pada Vue.js adalah fungsi khusus yang dipanggil pada tahap-tahap tertentu dalam siklus hidup komponen, 
        seperti saat komponen dibuat, dipasang (*mounted*), diperbarui, atau dihancurkan. Ini memungkinkan developer menjalankan 
        logika tertentu di waktu yang tepat, seperti pengambilan data dari API, manipulasi DOM, atau pembersihan resource.
      </p>
    </div>

    <div class="lifecycle-demo">
      <p ref="pElementRef" class="mounted-box">Menunggu mounted...</p>
    </div>
  </div>
</template>

<style scoped>
.lifecycle-container {
  display: flex;
  justify-content: space-between;
  gap: 32px;
  background-color: #f8fafc;
  padding: 32px;
  border-radius: 12px;
  margin: 32px;
  align-items: flex-start;
}

.lifecycle-text {
  flex: 2;
  font-size: 1.1em;
  color: #2d3748;
  line-height: 1.6;
}

.lifecycle-text h1 {
  font-size: 2em;
  color: #1a202c;
  margin-bottom: 16px;
}

.lifecycle-demo {
  flex: 1;
  background-color: #fff;
  padding: 24px;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  border: 1px solid #e2e8f0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.mounted-box {
  padding: 16px 24px;
  background-color: #edf2f7;
  border-radius: 8px;
  font-size: 1.2em;
  color: #2d3748;
  text-align: center;
}
</style>
