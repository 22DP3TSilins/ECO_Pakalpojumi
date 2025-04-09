<template>
  <div class="products">
    <h2>Our Eco Products</h2>
    <transition-group name="fade" tag="div" class="product-grid">
      <ProductCard
        v-for="(product, index) in products"
        :key="index"
        :title="product.title"
        :description="product.description"
        :image="product.image"
      />
    </transition-group>
  </div>
</template>

<script>
import ProductCard from '../components/ProductCard.vue'

export default {
  components: {
    ProductCard
  },
  data() {
    return {
      products: [
        { 
          title: "Eco Soap", 
          description: "Made with 100% natural ingredients", 
          image: "/src/assets/products/soap.jpg" 
        },
        { 
          title: "Reusable Bottle", 
          description: "Stainless steel, eco-friendly", 
          image: "/src/assets/products/bottle.jpg" 
        },
        { 
          title: "Bamboo Toothbrush", 
          description: "Sustainable and biodegradable", 
          image: "/src/assets/products/toothbrush.jpg" 
        },
        { 
          title: "Organic Cotton Bag", 
          description: "Say no to plastic bags", 
          image: "/src/assets/products/bag.jpg" 
        },
      ]
    }
  }
}
</script>

<style scoped>
.products {
  padding: 2rem;
  text-align: center;
}

.product-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
  margin-top: 2rem;
}

/* Fade animation */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
