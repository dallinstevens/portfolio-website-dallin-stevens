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
  position: sticky;
  top: 0;
  z-index: 1000;
  text-align: center;
  align-items: center;
  background-color: var(--color-background);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  width: 100%;
}

.header-content {
  display: flex;
  justify-content: center;
  padding: 1rem;
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
  display: flex;
  justify-content: center;
}
</style>
