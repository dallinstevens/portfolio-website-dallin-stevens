<template>
  <h1 class="cert-heading"><b>Certifications</b></h1>
  <div class="card-grid">
    <Card v-for="(card, index) in cards" :key="index">
      <template #logo>
        <a :href="card.url" target="_blank"><img :src="card.logo" alt="Logo" /></a>
      </template>
    </Card>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Card from '@/components/Cert.vue'

const cards = ref([
  {
    logo: '../src/assets/certs/aws-sap.png',
    url: 'https://www.credly.com/badges/811ad247-ad2b-4c44-8978-62743fb8fb95'
  },
  {
    logo: '../src/assets/certs/terraform-associate.png',
    url: 'https://www.credly.com/earner/earned/badge/034e10dd-46e3-477c-b135-c7796b25b1ae'
  },
  {
    logo: '../src/assets/certs/comptia-sec+.png',
    url: 'https://www.credly.com/earner/earned/badge/320092f3-4e20-4901-be6a-6e075a102c0c'
  },
  {
    logo: '../src/assets/certs/azure-fundamentals.png',
    url: 'https://learn.microsoft.com/en-us/users/dallinstevens-4460/credentials/e59a8ff14c285687'
  },
  {
    logo: '../src/assets/certs/google-cybersecurity.png',
    url: 'https://www.credly.com/earner/earned/badge/9b693082-feaf-4159-8a0e-0a8497e4b9bc'
  },
  {
    logo: '../src/assets/certs/aws-saa.png',
    url: 'https://www.credly.com/earner/earned/badge/2f3f1496-6e84-4d6a-8439-1a852de4d8a5'
  },
  {
    logo: '../src/assets/certs/cybersecurity-dual.png',
    url: 'https://www.credly.com/earner/earned/badge/320092f3-4e20-4901-be6a-6e075a102c0c'
  }
])
</script>

<style scoped>
.card-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
  padding: 16px;
}

.card-grid > *:nth-last-child(1):nth-child(3n + 1) {
  grid-column: 2 / 3;
}

.cert-heading {
  font-size: 2.5em;
  font-weight: bold;
  text-align: center;
  margin-bottom: 20px;
  text-shadow: 8px 8px 8px rgba(0, 0, 0, 0.1);
}
</style>
