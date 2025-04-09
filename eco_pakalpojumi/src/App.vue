<template>
  <div :class="{'dark-mode': isDarkMode}">
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/products">Products</router-link> |
      <router-link to="/contact">Contact</router-link> 
      |
      <button @click="toggleDarkMode" class="toggle-btn">
        {{ isDarkMode ? '☀️ Light' : '🌙 Dark' }}
      </button>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  data() {
    return {
      isDarkMode: false
    }
  },
  created() {
    // Check if user already selected dark mode
    const darkMode = localStorage.getItem('darkMode')
    this.isDarkMode = darkMode === 'true'
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode
      localStorage.setItem('darkMode', this.isDarkMode)
    }
  }
}
</script>

<style>
/* Global Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Light Mode */
body {
  font-family: 'Poppins', sans-serif;
  background: #f5f5f5;
  color: #333;
  min-height: 100vh;
}

/* Navbar */
nav {
  padding: 1rem 2rem;
  background: #4CAF50;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

nav a {
  color: white;
  text-decoration: none;
  font-weight: 600;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  transition: background 0.3s;
}

nav a:hover {
  background: rgba(255, 255, 255, 0.2);
}

/* Dark Mode */
.dark-mode {
  background: #121212;
  color: #eee;
}

.dark-mode nav {
  background: #1e1e1e;
}

.dark-mode nav a {
  color: #eee;
}

.toggle-btn {
  background: #ffffff33;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 8px;
  color: white;
  cursor: pointer;
  font-weight: 600;
  transition: background 0.3s;
}

.toggle-btn:hover {
  background: rgba(255, 255, 255, 0.4);
}

.dark-mode .toggle-btn {
  background: #333333;
}

.dark-mode .toggle-btn:hover {
  background: #555555;
}

/* Page Layout */
#app {
  padding-top: 4rem;
}

.router-view {
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
