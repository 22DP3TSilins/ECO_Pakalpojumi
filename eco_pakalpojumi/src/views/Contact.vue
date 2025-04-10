<template>
  <div class="contact">
    <h2>Contact Us</h2>
    <form action="https://formspree.io/f/xaneadno" method="POST" class="contact-form">
  <input type="text" name="name" placeholder="Your Name" required />
  <input type="email" name="email" placeholder="Your Email" required />
  <textarea name="message" placeholder="Your Message" required></textarea>
  <button type="submit">Send Message</button>
</form>

    <p v-if="successMessage" class="success">{{ successMessage }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      message: '',
      successMessage: ''
    }
  },
  methods: {
    submitForm() {
      // Simulate form submission
      this.successMessage = "Thank you, " + this.name + "! Your message has been sent.";
      // Clear form fields
      this.name = '';
      this.email = '';
      this.message = '';
    }
  }
}
</script>

<style scoped>
.contact {
  padding: 2rem;
  text-align: center;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-top: 2rem;
  max-width: 400px;
  margin-left: auto;
  margin-right: auto;
}

.contact-form input,
.contact-form textarea {
  padding: 0.8rem;
  border-radius: 10px;
  border: 1px solid #ccc;
  font-size: 1rem;
}

.contact-form button {
  padding: 0.8rem;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 10px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
}

.contact-form button:hover {
  background-color: #45a049;
}

.success {
  color: #4CAF50;
  margin-top: 1rem;
  font-weight: bold;
}

/* Dark mode support */
.dark-mode .contact-form input,
.dark-mode .contact-form textarea {
  background: #2a2a2a;
  border: 1px solid #666;
  color: white;
}

.dark-mode .contact-form button {
  background: #81c784;
  color: #1f1f1f;
}

.dark-mode .contact-form button:hover {
  background: #66bb6a;
}
</style>
