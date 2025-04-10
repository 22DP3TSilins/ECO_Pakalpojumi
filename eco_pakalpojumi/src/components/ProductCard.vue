<template>
  <div class="card">
    <img :src="image" alt="Product image" class="product-image" />
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <button class="learn-more-btn">Learn More</button> <!-- 👈 Button added -->
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    description: String,
    image: String,
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
  width: 250px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card:hover {
  transform: scale(1.05);
  background: #e8f5e9;
}

.product-image {
  width: 100%;
  max-height: 200px;
  object-fit: contain;
  border-radius: 10px;
  margin-bottom: 1rem;
}

.learn-more-btn {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  background: #4CAF50;
  border: none;
  color: white;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  transition: background 0.3s;
}

.learn-more-btn:hover {
  background: #45a049;
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

.dark-mode .learn-more-btn {
  background: #81c784;
  color: #1f1f1f;
}

.dark-mode .learn-more-btn:hover {
  background: #66bb6a;
}
</style>
