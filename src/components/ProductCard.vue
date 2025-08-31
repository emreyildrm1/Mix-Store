<template>
    <div class="card">
      <img :src="product.image" alt="Ürün görseli" class="product-img" />

      <h3>{{ product.title }}</h3>
  
      <p class="price">{{ product.price }} TL</p>
  
      <button class="add-btn">Sepete Ekle</button>
    </div>
  </template>
  
  <script setup>
  // Bu bileşene dışarıdan "product" adında bir veri (props) gönderileceğini söylüyoruz
  // Yani ProductsPage.vue’den gelen her ürünün bilgisi buraya aktarılacak
  defineProps({
    product: Object
  });
  </script>
  
  <style scoped>
  .card {
    border: 1px solid #dbe8ff;
    border-radius: 8px;
    padding: 15px;
    text-align: center;
    transition: 0.3s; 
  }
  
  .card:hover {
    box-shadow: 0px 2px 10px rgba(0,0,0,0.15);
  }

  .product-img {
    max-width: 150px;
    height: auto;
  }
  
  .price {
    font-weight: bold;
    color: #27ae60;
  }
  
  .add-btn {
    margin-top: 10px;
    background: #ff6600;
    color: white;
    border: none;
    padding: 8px 12px;
    border-radius: 6px; 
    cursor: pointer; 
  }
  </style>
  