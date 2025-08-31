<template>
  <div id="app">
    <header class="header">
      <h1>Emre Store</h1>
    </header>

    <main>
      <ProductsPage />
    </main>

    <footer class="footer">
      <p>© 2025 Emre Store - Emre Yıldırım</p>
    </footer>
  </div>
</template>

<script setup>
import ProductsPage from "./pages/ProductsPage.vue";
</script>

<style scoped>
#app {
  font-family: Arial, sans-serif;
  background: #ffffff;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.header {
  background: #bcbcbc;
  color: rgb(0, 0, 0);
  padding: 15px;
  text-align: center;
}

main {
  flex: 1;
  padding: 20px;
}

.footer {
  background: #222;
  color: white;
  text-align: center;
  padding: 10px;
  font-size: 14px;
}
</style>
