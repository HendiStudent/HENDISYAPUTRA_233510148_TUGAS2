<!-- File: src/components/Home.vue -->
<template>
  <div class="home">
    <h2>Selamat Datang di Pembelajaran Vue.js!</h2>
    <p>
      Ini adalah halaman <strong>Home</strong> dari modul pertemuan 2 dan 3. 
      Di sini kamu akan mempelajari berbagai fitur dasar Vue.js, mulai dari declarative rendering hingga watchers.
    </p>
    <ul>
      <li>Memahami konsep rendering deklaratif</li>
      <li>Menggunakan binding atribut dan form</li>
      <li>Mengontrol tampilan dengan conditional rendering</li>
      <li>Mengelola data dengan computed property dan watchers</li>
    </ul>
    <p>
      Gunakan menu di sebelah kiri untuk mengeksplorasi materi secara interaktif.
    </p>
  </div>
</template>

<script>
export default {
  name: 'Home'
};
</script>

<style scoped>
.home {
  background: white;
  padding: 24px;
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
}

.home h2 {
  color: #0f172a;
  font-size: 24px;
  margin-bottom: 12px;
}

.home p {
  color: #334155;
  margin-bottom: 12px;
  line-height: 1.6;
}

.home ul {
  list-style: disc;
  margin-left: 20px;
  margin-bottom: 16px;
}

.home li {
  margin-bottom: 6px;
}
</style>
