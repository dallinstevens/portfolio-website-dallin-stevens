<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 0
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <div class="app-container">
    <header :class="{ scrolled: isScrolled }">
      <div class="header-content">
        <!-- Add an image to the left side of the header -->
        <img src="./assets/logo4.png" alt="Logo" class="header-logo" />
        <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
          <RouterLink to="/certificates">Certificates</RouterLink>
        </nav>
      </div>
    </header>

    <main>
      <RouterView />
    </main>
  </div>
</template>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  align-items: center;
}

header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background-color: var(--color-background);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: border-bottom 0.3s;
}

header.scrolled {
  border-bottom: 2px solid var(--color-border); /* Add a border when scrolled */
}

.header-content {
  display: flex;
  justify-content: space-between; /* Change to space-between to separate logo and nav */
  align-items: center; /* Center items vertically */
  padding: 1rem;
  max-width: 1200px;
  margin: 0 auto;
}

.header-logo {
  height: 40px; /* Adjust the size of the logo as needed */
}

nav {
  display: flex;
  gap: 2rem;
}

nav a {
  color: var(--color-text);
  text-decoration: none;
  font-weight: bold;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  transition: background-color 0.3s;
}

nav a:hover,
nav a.router-link-active {
  background-color: var(--color-background-soft);
}

main {
  flex-grow: 1;
  padding: 2rem;
  max-width: 1200px;
  width: 100%;
  text-align: center;
  margin-top: 30px;
}
</style>
