<script>
import vueLogo from '../assets/vue.svg'
export default {
  name: 'Home'
}
</script>

<template>
  <div class="home-container">
    <img src="/src/assets/vue.svg" alt="Vue Logo" class="vue-logo" />

    <div class="home-content">
      <h1>Selamat Datang di Pembelajaran Vue.js!</h1>
      <p>
        Halaman <strong>Home</strong> ini merupakan pengantar materi pada pertemuan 2 dan 3. Kamu akan mempelajari berbagai konsep penting dalam Vue.js secara bertahap dan interaktif.
      </p>

      <div class="learning-points">
        <h2>Yang Akan Kamu Pelajari:</h2>
        <ul>
          <li>Konsep rendering deklaratif</li>
          <li>Binding atribut dan formulir</li>
          <li>Conditional rendering untuk kontrol tampilan</li>
          <li>Penggunaan computed property dan watchers</li>
        </ul>
      </div>

      <p>
        Gunakan menu navigasi di sebelah kiri untuk mulai menjelajahi topik secara mendalam.
      </p>
    </div>
  </div>
</template>

<style scoped>
.home-container {
  max-width: 860px;
  margin: 40px auto;
  padding: 32px;
  background-color: #ffffff;
  border-radius: 16px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.06);
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.vue-logo {
  display: block;
  margin: 0 auto 24px;
  width: 100px;
  height: 100px;
  animation: spin 20s linear infinite;
}

.home-content h1 {
  font-size: 2em;
  color: #1e293b;
  margin-bottom: 16px;
}

.home-content h2 {
  font-size: 1.3em;
  color: #334155;
  margin-bottom: 10px;
  margin-top: 24px;
}

.home-content p {
  font-size: 1.05em;
  color: #475569;
  margin-bottom: 16px;
  line-height: 1.6;
}

.learning-points ul {
  list-style: disc;
  padding-left: 20px;
  margin-bottom: 24px;
}

.learning-points li {
  margin-bottom: 8px;
  font-size: 1em;
  color: #334155;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
