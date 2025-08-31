<template>
    <div class="products">
      <ProductCard v-for="(product, index) in products" :key="index" :product="product"/>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from "vue";  // ref dinamik değişkenler için, onMounted ise sayfada öncelikli yükleme için
  
  import ProductCard from "../components/ProductCard.vue";
  
  const products = ref([]); // dinamik boş bir dizi yapıp bu diziyi çekilen veri ile dolduracaz
  

  onMounted(async () => { //sayfa çalıştığında ilk yüklenenecek öğe
    try {
      const response = await fetch("https://fakestoreapi.com/products");  // API'den ürün verilerini çekiyoruz
  
     
      const data = await response.json();  // Veriyi JSON formatına çeviriyoruz
  
      products.value = data.slice(0, 8); // ilk 8 tanesini alıyoruz
    } catch (error) {
      
      console.error("Veri çekilemedi:", error);// Eğer hata olursa konsola yazdırıyoruz
    }
  });
  </script>
  
  <style scoped>
  .products {
    display: grid;
    grid-template-columns: repeat(4, 1fr); /* 4 sütun olacak */
    gap: 20px; /* ürünler arası boşluk */
    padding: 20px; 
  }
  </style>
  