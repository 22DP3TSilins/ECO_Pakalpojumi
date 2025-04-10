<template>
  <div class="card">
    <img :src="image" alt="Product image" class="product-image" />
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <button class="learn-more-btn" @click="openModal">Learn More</button>
  </div>

  <!-- 👇 Move the modal OUTSIDE the card -->
  <transition name="zoom">
    <div v-if="showModal" class="modal-overlay" @click.self="closeModal">
      <div class="modal-content">
        <h2>{{ title }}</h2>
        <p>{{ fullDescription }}</p>
        <button @click="closeModal" class="close-btn">Close</button>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    title: String,
    description: String,
    image: String,
    fullDescription: {
      type: String,
      default: "This is a more detailed description of the product."
    }
  },
  data() {
    return {
      showModal: false
    }
  },
  methods: {
    openModal() {
      this.showModal = true
    },
    closeModal() {
      this.showModal = false
    }
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
  position: relative;
}

.card:hover {
  transform: scale(1.05);
  background: #e8f5e9;
}

/* Disable hover if modal is open */
.card.modal-open:hover {
  transform: none;
  background: inherit;
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

/* Modal Popup */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background: white;
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
  max-width: 400px;
  width: 80%;
}

.close-btn {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  background: #f44336;
  border: none;
  color: white;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
}

.close-btn:hover {
  background: #d32f2f;
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

.dark-mode .modal-content {
  background: #2a2a2a;
  color: #eee;
}

.dark-mode .learn-more-btn {
  background: #81c784;
  color: #1f1f1f;
}

.dark-mode .learn-more-btn:hover {
  background: #66bb6a;
}

/* Zoom Animation */
.zoom-enter-active, .zoom-leave-active {
  transition: all 0.3s ease;
}

.zoom-enter-from, .zoom-leave-to {
  opacity: 0;
  transform: scale(0.8);
}


</style>
