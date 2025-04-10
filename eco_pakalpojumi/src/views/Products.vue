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
        :fullDescription="product.fullDescription"
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
          description: "Made with natural ingredients", 
          image: "/src/assets/products/soap.jpg",
          fullDescription: "Our Eco Soap is handcrafted with 100% organic ingredients, safe for all skin types and environmentally friendly."
        },
        { 
          title: "Reusable Bottle", 
          description: "Eco-friendly stainless steel", 
          image: "/src/assets/products/bottle.jpg",
          fullDescription: "Our Reusable Bottle keeps your drinks cold or hot for hours and reduces plastic waste. Join the eco revolution!"
        },
        { 
          title: "Bamboo Toothbrush", 
          description: "Sustainable and biodegradable", 
          image: "/src/assets/products/toothbrush.jpg",
          fullDescription: "Our Bamboo Toothbrush is a sustainable alternative to plastic. Natural, biodegradable and great for your smile!"
        },
        { 
          title: "Organic Cotton Bag", 
          description: "Say no to plastic bags", 
          image: "/src/assets/products/bag.jpg",
          fullDescription: "Carry your groceries or essentials in style with our Organic Cotton Bag. Durable, washable, and eco-friendly."
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
</style>
