<script setup>
import { ref, computed } from 'vue'
import { categories, photos } from '../data/ambientes.js'

const activeFilter = ref('todos')
const lightbox = ref(null)

const filtered = computed(() =>
  activeFilter.value === 'todos'
    ? photos
    : photos.filter(p => p.category === activeFilter.value)
)

function openLightbox(photo) {
  lightbox.value = photo
  document.body.style.overflow = 'hidden'
}

function closeLightbox() {
  lightbox.value = null
  document.body.style.overflow = ''
}

function onKeydown(e) {
  if (e.key === 'Escape') closeLightbox()
}
</script>

<template>
  <section id="ambientes" class="ambientes" @keydown.esc="closeLightbox">

    <div class="ambientes__container">

      <!-- Cabeçalho -->
      <div class="ambientes__header">
        <span class="ambientes__label">Nossos Trabalhos</span>
        <h2 class="ambientes__title">Ambientes que inspiram</h2>
        <p class="ambientes__desc">
          Veja como as pedras naturais transformam cada espaço — escolha uma categoria e explore os projetos.
        </p>
      </div>

      <!-- Filtros -->
      <div class="ambientes__filters">
        <button
          v-for="cat in categories"
          :key="cat.key"
          class="filter__btn"
          :class="{ active: activeFilter === cat.key }"
          @click="activeFilter = cat.key"
        >
          {{ cat.label }}
        </button>
      </div>

      <!-- Mosaico -->
      <div class="gallery" :key="activeFilter">
        <div
          v-for="photo in filtered"
          :key="photo.id"
          class="gallery__item"
          @click="openLightbox(photo)"
        >
          <img :src="photo.src" :alt="photo.alt" loading="lazy" />
          <div class="gallery__overlay">
            <span class="gallery__zoom">&#8599;</span>
          </div>
        </div>
      </div>

    </div>

    <!-- Lightbox -->
    <Transition name="lb">
      <div v-if="lightbox" class="lightbox" @click.self="closeLightbox" @keydown.window.esc="closeLightbox">
        <button class="lightbox__close" @click="closeLightbox" aria-label="Fechar">&#10005;</button>
        <img :src="lightbox.src" :alt="lightbox.alt" class="lightbox__img" />
        <p class="lightbox__caption">{{ lightbox.alt }}</p>
      </div>
    </Transition>

  </section>
</template>

<style scoped>
.ambientes {
  background-color: #fff;
  padding: 5rem 1.5rem;
}

.ambientes__container {
  max-width: 1200px;
  margin: 0 auto;
}

/* ── Cabeçalho ── */
.ambientes__header {
  text-align: center;
  margin-bottom: 2.5rem;
}

.ambientes__label {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #A88A5A;
  margin-bottom: 0.75rem;
}

.ambientes__title {
  font-size: clamp(1.6rem, 3vw, 2.4rem);
  font-weight: 700;
  color: #2c2c2c;
  margin: 0 0 1rem;
}

.ambientes__desc {
  color: #777;
  font-size: 1rem;
  max-width: 560px;
  margin: 0 auto;
  line-height: 1.7;
}

/* ── Filtros ── */
.ambientes__filters {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.6rem;
  margin-bottom: 2.5rem;
}

.filter__btn {
  padding: 0.5rem 1.4rem;
  border: 1.5px solid #d6c9b0;
  background: transparent;
  color: #888;
  font-family: 'Raleway', sans-serif;
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  cursor: pointer;
  border-radius: 2px;
  transition: all 0.25s ease;
}

.filter__btn:hover {
  border-color: #A88A5A;
  color: #A88A5A;
}

.filter__btn.active {
  background-color: #A88A5A;
  border-color: #A88A5A;
  color: #fff;
}

/* ── Mosaico ── */
.gallery {
  columns: 3;
  column-gap: 1rem;
  animation: galleryFadeIn 0.4s ease;
}

@keyframes galleryFadeIn {
  from { opacity: 0; transform: translateY(8px); }
  to   { opacity: 1; transform: translateY(0); }
}

.gallery__item {
  break-inside: avoid;
  margin-bottom: 1rem;
  position: relative;
  cursor: pointer;
  overflow: hidden;
  border-radius: 3px;
}

.gallery__item img {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.4s ease;
}

.gallery__overlay {
  position: absolute;
  inset: 0;
  background: rgba(168, 138, 90, 0);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.3s ease;
}

.gallery__zoom {
  color: #fff;
  font-size: 2rem;
  opacity: 0;
  transform: scale(0.7);
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.gallery__item:hover img {
  transform: scale(1.04);
}

.gallery__item:hover .gallery__overlay {
  background: rgba(168, 138, 90, 0.45);
}

.gallery__item:hover .gallery__zoom {
  opacity: 1;
  transform: scale(1);
}

/* ── Lightbox ── */
.lightbox {
  position: fixed;
  inset: 0;
  z-index: 1000;
  background: rgba(0, 0, 0, 0.92);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  cursor: zoom-out;
}

.lightbox__img {
  max-width: 90vw;
  max-height: 82vh;
  object-fit: contain;
  border-radius: 3px;
  cursor: default;
}

.lightbox__caption {
  color: rgba(255,255,255,0.65);
  font-size: 0.85rem;
  margin-top: 1rem;
  text-align: center;
  letter-spacing: 0.5px;
}

.lightbox__close {
  position: absolute;
  top: 1.25rem;
  right: 1.5rem;
  background: none;
  border: none;
  color: #fff;
  font-size: 1.4rem;
  cursor: pointer;
  opacity: 0.7;
  transition: opacity 0.2s;
  padding: 0.25rem 0.5rem;
}

.lightbox__close:hover {
  opacity: 1;
}

/* Lightbox transition */
.lb-enter-active,
.lb-leave-active {
  transition: opacity 0.3s ease;
}
.lb-enter-from,
.lb-leave-to {
  opacity: 0;
}

/* ── Responsivo ── */
@media (max-width: 900px) {
  .gallery { columns: 2; }
}

@media (max-width: 540px) {
  .gallery { columns: 1; }
  .ambientes { padding: 3.5rem 1rem; }
}
</style>
