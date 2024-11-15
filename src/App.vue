<template>
  <div id="app">
    <div class="background"></div>
    <div class="content">
      <h2 class="comment-section-title">Comment Section</h2>
      <CommentList />
    </div>
  </div>
</template>

<script>
import CommentList from './components/CommentList.vue'

export default {
  name: 'App',
  components: {
    CommentList
  }
}
</script>

<style>
/* Pastikan html dan body menutupi seluruh layar */
html, body {
  margin: 0;
  padding: 0;
  height: 100%;  /* Pastikan body mengambil seluruh tinggi layar */
  width: 100%;   /* Pastikan body mengambil seluruh lebar layar */
}

/* Mengatur #app untuk menutupi seluruh layar */
#app {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}

/* Background full putih */
.background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #ffffff;  /* Background menjadi putih */
  z-index: -1;  /* Pastikan background di belakang konten */
}

/* Konten */
.content {
  position: relative;
  z-index: 1;
  padding: 20px;
  text-align: center;
  flex-grow: 1;  /* Membuat konten mengisi ruang yang tersisa */
}

/* Judul */
.comment-section-title {
  font-size: 2rem;
  font-weight: bold;
  color: #000000;
  margin-bottom: 20px;
}
</style>
