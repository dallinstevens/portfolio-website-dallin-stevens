<!-- TODO: Combine with Card.vue -->
<!-- TODO: Change card animation to flip and grow big. Have link to click to verify -->

<template>
  <div class="cert">
    <div class="cert-inner">
      <div class="cert-front">
        <div class="logo-container">
          <slot name="logo"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.cert {
  width: 200px;
  height: 200px;
  perspective: 1000px;
  user-select: none;
  cursor: pointer;
  transition: transform 0.3s;
}

.cert:hover {
  transform: scale(1.1); /* Scale effect */
}

.cert-inner {
  width: 100%;
  height: 100%;
  position: relative;
}

.cert-front {
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 18px;
  overflow: hidden;
  background-color: transparent;
}

.logo-container {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 15px;
  background-color: transparent;
}

.logo-container :deep(img) {
  max-width: 90%;
  max-height: 90%;
  object-fit: contain;
}

.logo-container :deep(a) {
  background-color: transparent;
}

.logo-container :deep(a:hover) {
  background-color: transparent;
}
</style>
