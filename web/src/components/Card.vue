<template>
  <div class="card" @mouseover="flipped = true" @mouseleave="flipped = false">
    <div class="card-inner" :class="{ flipped: flipped }">
      <div class="card-front">
        <div class="logo-container">
          <slot name="logo"></slot>
        </div>
      </div>
      <div class="card-back">
        <div class="description-container">
          <slot name="description"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const flipped = ref(false)
</script>

<style scoped>
.card {
  --card-bg-color: var(--color-background);
  --card-text-color: var(--color-text);
  --card-border-color: var(--color-text);

  width: 120px;
  height: 120px;
  perspective: 1000px;
  user-select: none;
  cursor: pointer;
}

.card-inner {
  width: 100%;
  height: 100%;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  position: relative;
  border-radius: 20px;
  border: 2px solid var(--card-border-color);
}

.card-inner.flipped {
  transform: rotateY(180deg);
}

.card-front,
.card-back {
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
  background-color: var(--card-bg-color);
  color: var(--card-text-color);
}

.card-back {
  transform: rotateY(180deg);
}

.logo-container,
.description-container {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 15px;
}

.logo-container :deep(img) {
  max-width: 90%;
  max-height: 90%;
  object-fit: contain;
  pointer-events: none;
}

.description-container {
  text-align: center;
  overflow-y: auto;
}

:deep(.card-back *) {
  user-select: none;
}
</style>
