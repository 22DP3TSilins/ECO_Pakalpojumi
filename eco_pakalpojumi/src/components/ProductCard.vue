<template>
    <div class="card">
      <img :src="image" alt="Product image" class="product-image" />
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
      description: String,
      image: String, // 👈 new prop
    }
  }
  </script>
  
  <style scoped>
  .card {
    background: white;
    color: #333;
    border: 2px solid #4CAF50;
    border-radius: 15px;
    padding: 1rem;
    text-align: center;
    transition: transform 0.3s, background 0.3s, color 0.3s;
    width: 300px; /* Make card a little wider */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .card:hover {
    transform: scale(1.05);
    background: #e8f5e9;
  }
  
  .product-image {
    width: 100%;
    height: auto;
    max-height: 250px;
    object-fit: contain; /* 👈 change from cover to contain */
    border-radius: 10px;
    margin-bottom: 1rem;
  }

  
  /* Dark mode support */
  .dark-mode .card {
    background: #1f1f1f;
    color: #eee;
    border-color: #81c784;
  }
  
  .dark-mode .card:hover {
    background: #2e2e2e;
  }
  </style>
  