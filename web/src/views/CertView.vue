<template>
  <h1>Certifications</h1>
  <div class="card-grid">
    <Card v-for="(card, index) in cards" :key="index">
      <template #logo>
        <img :src="card.logo" alt="Logo" />
      </template>
      <template #description>
        <p>{{ card.description }}</p>
      </template>
    </Card>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Card from '@/components/Card.vue'

const cards = ref([
  { logo: '../src/assets/aws.png', description: 'Description 1' },
  { logo: '../src/assets/azure.png', description: 'Description 2' }
])
</script>

<style scoped>
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 16px;
  padding: 16px;
}
</style>
