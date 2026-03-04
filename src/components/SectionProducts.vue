<script setup>
import { products } from '../data/products.js'
</script>

<template>
  <section id="produtos" class="products">
    <div class="products__container">

      <div class="products__header">
        <span class="products__label">Catálogo</span>
        <h2 class="products__title">Nossas Pedras</h2>
        <button class="btn-ver-mais">Ver mais</button>
      </div>

      <div class="products__grid">
        <div
          v-for="product in products"
          :key="product.id"
          class="card"
        >
          <div class="card__image">
            <img
              v-if="product.image"
              :src="product.image"
              :alt="product.name"
            />
            <div v-else class="card__placeholder" />
          </div>

          <div class="card__body">
            <h3 class="card__name">{{ product.name }}</h3>
            <div class="card__divider" />
            <p class="card__sizes-label">Medidas disponíveis</p>
            <ul class="card__sizes">
              <li v-for="size in product.sizes" :key="size">{{ size }}</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="products__footer">
        <button class="btn-ver-mais">Ver mais</button>
      </div>

    </div>
  </section>
</template>

<style scoped>
.products {
  padding: 6rem 1.5rem;
  background-color: #F8F6F3;
}

.products__container {
  max-width: 1100px;
  margin: 0 auto;
}

.products__header {
  text-align: center;
  margin-bottom: 3.5rem;
}

.products__label {
  display: block;
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #A88A5A;
  margin-bottom: 0.75rem;
}

.products__title {
  font-size: clamp(1.6rem, 3vw, 2.2rem);
  font-weight: 700;
  color: #1C1C1C;
  margin-bottom: 1.5rem;
}

.btn-ver-mais {
  display: inline-block;
  padding: 0.65rem 2rem;
  font-family: 'Raleway', sans-serif;
  font-size: 0.85rem;
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: #A88A5A;
  background-color: transparent;
  border: 2px solid #A88A5A;
  border-radius: 3px;
  cursor: pointer;
  transition: background-color 0.2s, color 0.2s;
}

.btn-ver-mais:hover {
  background-color: #A88A5A;
  color: #fff;
}

.products__footer {
  text-align: center;
  margin-top: 3rem;
}

.products__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.card {
  background-color: #fff;
  border: 1px solid #EDE8DF;
  border-radius: 4px;
  overflow: hidden;
  transition: box-shadow 0.25s, transform 0.25s;
}

.card:hover {
  box-shadow: 0 8px 24px rgba(168, 138, 90, 0.12);
  transform: translateY(-4px);
}

.card__image {
  width: 100%;
  aspect-ratio: 4 / 3;
  overflow: hidden;
  background-color: #F0EBE1;
}

.card__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.card:hover .card__image img {
  transform: scale(1.04);
}

.card__placeholder {
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #EDE8DF 0%, #DDD5C8 100%);
}

.card__body {
  padding: 1.25rem 1.5rem 1.5rem;
}

.card__name {
  font-size: 1rem;
  font-weight: 700;
  color: #1C1C1C;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.card__divider {
  width: 32px;
  height: 2px;
  background-color: #A88A5A;
  margin: 0.75rem 0;
}

.card__sizes-label {
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: #999;
  margin-bottom: 0.5rem;
}

.card__sizes {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  padding: 0;
  margin: 0;
}

.card__sizes li {
  font-size: 0.78rem;
  color: #555;
  background-color: #F5F0E8;
  padding: 0.2rem 0.6rem;
  border-radius: 2px;
}

@media (max-width: 768px) {
  .products__grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 480px) {
  .products__grid {
    grid-template-columns: 1fr;
  }
}
</style>
