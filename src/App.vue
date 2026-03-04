<script setup>
import TheHeader from './components/TheHeader.vue'
import TheCarousel from './components/TheCarousel.vue'
import SectionAbout from './components/SectionAbout.vue'
import SectionProducts from './components/SectionProducts.vue'
import SectionAmbientes from './components/SectionAmbientes.vue'
import SectionContact from './components/SectionContact.vue'
import WhatsAppButton from './components/WhatsAppButton.vue'
import TheFooter from './components/TheFooter.vue'
</script>

<template>
  <TheHeader />

  <main class="main">
    <TheCarousel />
    <SectionAbout />
    <SectionProducts />
    <SectionAmbientes />
    <SectionContact />
  </main>

  <WhatsAppButton />
  <TheFooter />
</template>

<style scoped>
.main {
  padding-top: 148px;
}
</style>
