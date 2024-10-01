<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="app-container">
    <header>
      <div class="header-content">
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
}

.header-content {
  display: flex;
  justify-content: center;
  padding: 1rem;
  max-width: 1200px;
  margin: 0 auto;
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
  margin-top: 60px; /* Adjust this value based on your header height */
}
</style>
