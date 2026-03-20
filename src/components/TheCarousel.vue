<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

import img1 from '../assets/carousel/carrossel1.jpg'
import img2 from '../assets/carousel/carrossel2.jpg'
import img3 from '../assets/carousel/carrossel3.jpg'
import img4 from '../assets/carousel/carrossel4.jpg'
import img5 from '../assets/carousel/carrossel5.jpg'
import img6 from '../assets/carousel/carrossel6.jpg'
import img7 from '../assets/carousel/carrossel7.jpg'
import img8 from '../assets/carousel/carrossel8.jpg'

const images = [img1, img2, img3, img4, img5, img6, img7, img8]

const current = ref(0)
let autoplay = null

function prev() {
  current.value = (current.value - 1 + images.length) % images.length
}

function next() {
  current.value = (current.value + 1) % images.length
}

function goTo(index) {
  current.value = index
}

onMounted(() => {
  autoplay = setInterval(next, 5000)
})

onUnmounted(() => {
  clearInterval(autoplay)
})
</script>

<template>
  <section id="inicio" class="hero">

    <div class="hero__slides">
      <img
        v-for="(img, index) in images"
        :key="index"
        :src="img"
        :alt="`Obra Pedras Boa Vista - ${index + 1}`"
        class="hero__image"
        :class="{ active: index === current }"
      />
    </div>

    <div class="hero__overlay" />

    <div class="hero__content">
      <h1 class="hero__title">Beleza natural que<br />transforma ambientes</h1>
      <a href="#produtos" class="hero__cta">Ver Catálogo</a>
    </div>

    <button class="hero__btn hero__btn--prev" @click="prev" aria-label="Anterior">&#8592;</button>
    <button class="hero__btn hero__btn--next" @click="next" aria-label="Próximo">&#8594;</button>

    <div class="hero__dots">
      <button
        v-for="(img, index) in images"
        :key="index"
        class="hero__dot"
        :class="{ active: index === current }"
        @click="goTo(index)"
        :aria-label="`Imagem ${index + 1}`"
      />
    </div>

  </section>
</template>

<style scoped>
.hero {
  position: relative;
  width: 100%;
  height: 80vh;
  margin-top: 0;
  overflow: hidden;
}

.hero__slides {
  position: absolute;
  inset: 0;
}

.hero__image {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0;
  transition: opacity 1s ease;
}

.hero__image.active {
  opacity: 1;
}

.hero__overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.15) 0%,
    rgba(0, 0, 0, 0.55) 100%
  );
  z-index: 1;
}

.hero__content {
  position: absolute;
  inset: 0;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 1.5rem;
}

.hero__subtitle {
  font-size: 0.9rem;
  font-weight: 600;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: #A88A5A;
  margin-bottom: 1rem;
}

.hero__title {
  font-size: clamp(2rem, 5vw, 3.5rem);
  font-weight: 700;
  color: #ffffff;
  line-height: 1.2;
  margin-bottom: 2rem;
}

.hero__cta {
  display: inline-block;
  padding: 0.85rem 2.5rem;
  background-color: #A88A5A;
  color: #fff;
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  border-radius: 2px;
  transition: background-color 0.3s;
}

.hero__cta:hover {
  background-color: #886E45;
}

.hero__btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  z-index: 3;
  background: none;
  border: none;
  color: #fff;
  font-size: 2rem;
  cursor: pointer;
  transition: color 0.2s;
  padding: 0;
  width: 2.5rem;
  height: 2.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  text-shadow: 0 1px 4px rgba(0,0,0,0.4);
  line-height: 1;
}

.hero__btn:hover {
  color: #A88A5A;
}

.hero__btn--prev { left: 1.5rem; }
.hero__btn--next { right: 1.5rem; }

.hero__dots {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 8px;
  z-index: 3;
}

.hero__dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  border: 2px solid rgba(255, 255, 255, 0.7);
  background: transparent;
  cursor: pointer;
  transition: background-color 0.2s, border-color 0.2s;
}

.hero__dot.active {
  background-color: #A88A5A;
  border-color: #A88A5A;
}

@media (max-width: 600px) {
  .hero__btn { display: none; }
}
</style>
