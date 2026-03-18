<script setup>
const googleReviews = [
  {
    id: 1,
    name: 'Liziane Vieira',
    time: '2 anos atrás',
    rating: 5,
    text: 'Atendimento espetacular! Grande variedade de produtos, preço bom, entrega foi no prazo combinado e a colocação foi impecável. Superou minhas expectativas. Recomendo.',
  },
  {
    id: 2,
    name: 'Luiz Henrique Ruffino',
    time: '4 anos atrás',
    rating: 5,
    text: 'O compromisso da empresa para com o cliente foi muito satisfatório. Adquirimos Pedras Ferro e estávamos preocupados com a qualidade das pedras bem como com o serviço de colocação. Tudo ficou perfeito.',
  },
  {
    id: 3,
    name: 'Sybelle Sybelle',
    rating: 5,
    time: '4 anos atrás',
    text: 'Ótimo serviço! Entregas feitas sempre no prazo estabelecido, a colocação das pedras é perfeita e os valores são acessíveis!',
  },
]

function renderStars(rating) {
  const safeRating = Math.max(0, Math.min(5, Number(rating) || 0))
  return '★'.repeat(safeRating) + '☆'.repeat(5 - safeRating)
}
</script>

<template>
  <section id="contato" class="contact">
    <div class="contact__container">

      <div class="contact__header">
        <span class="contact__label">Fale Conosco</span>
        <h2 class="contact__title">Como nos encontrar</h2>
        <p class="contact__desc">
          Visite nossa loja ou entre em contato pelos canais abaixo. Será um prazer atendê-lo!
        </p>
      </div>

      <div class="contact__body">

        <div class="contact__info">

          <div class="info__card">
            <div class="info__icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#A88A5A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M21 10c0 7-9 13-9 13S3 17 3 10a9 9 0 1 1 18 0z"/>
                <circle cx="12" cy="10" r="3"/>
              </svg>
            </div>
            <div>
              <h4 class="info__title">Endereço</h4>
              <p class="info__text">Rua João Havro, 1349<br>Boa Vista, Curitiba – PR<br>CEP 82560-020</p>
            </div>
          </div>

          <div class="info__card">
            <div class="info__icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#A88A5A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.61 3.36 2 2 0 0 1 3.59 1.18l3-.07a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.75a16 16 0 0 0 5.95 5.95l1.63-1.63a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/>
              </svg>
            </div>
            <div>
              <h4 class="info__title">Telefone</h4>
              <p class="info__text">(41) 3256-7078</p>
            </div>
          </div>

          <div class="info__card">
            <div class="info__icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#A88A5A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <circle cx="12" cy="12" r="10"/>
                <polyline points="12 6 12 12 16 14"/>
              </svg>
            </div>
            <div>
              <h4 class="info__title">Horário de Funcionamento</h4>
              <p class="info__text">
                Segunda a Sexta<br>
                <strong>08h00 – 12h00</strong><br>
                <strong>13h00 – 18h00</strong>
              </p>
            </div>
          </div>

          <div class="info__card">
            <div class="info__icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="#25D366">
                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413z"/>
                <path d="M12 0C5.373 0 0 5.373 0 12c0 2.125.557 4.126 1.533 5.862L.057 23.428a.75.75 0 0 0 .921.921l5.666-1.476A11.94 11.94 0 0 0 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.75A9.741 9.741 0 0 1 6.7 20.2l-.387-.232-4.015 1.046 1.065-3.913-.253-.402A9.718 9.718 0 0 1 2.25 12C2.25 6.615 6.615 2.25 12 2.25S21.75 6.615 21.75 12 17.385 21.75 12 21.75z"/>
              </svg>
            </div>
            <div>
              <h4 class="info__title">WhatsApp</h4>
              <a
                href="https://wa.me/554132567078"
                target="_blank"
                rel="noopener"
                class="info__whatsapp"
              >Enviar mensagem</a>
            </div>
          </div>

        </div>

        <div class="contact__map">
          <iframe
            title="Localização Pedras Boa Vista"
            src="https://maps.google.com/maps?q=Rua+Jo%C3%A3o+Havro+1349+Boa+Vista+Curitiba+PR&t=&z=16&ie=UTF8&iwloc=B&output=embed"
            width="100%"
            height="100%"
            style="border:0;"
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
          ></iframe>
        </div>

      </div>

      <div class="reviews">
        <div class="reviews__header">
          <span class="reviews__label">Depoimentos</span>
          <h3 class="reviews__title">Avaliações no Google</h3>
        </div>

        <div class="reviews__grid">
          <article
            v-for="review in googleReviews"
            :key="review.id"
            class="review-card"
          >
            <div class="review-card__top">
              <strong class="review-card__name">{{ review.name }}</strong>
              <span class="review-card__time">{{ review.time }}</span>
            </div>
            <div class="review-card__stars" :aria-label="`${review.rating} estrelas`">{{ renderStars(review.rating) }}</div>
            <p class="review-card__text">{{ review.text }}</p>
          </article>
        </div>

        <a
          href="https://www.google.com/search?q=Pedras+Boa+Vista+Curitiba+avaliacoes"
          target="_blank"
          rel="noopener"
          class="reviews__link"
        >Ver mais avaliações no Google</a>
      </div>

    </div>
  </section>
</template>

<style scoped>
.contact {
  background-color: #F5EDD8;
  padding: 5rem 1.5rem;
}

.contact__container {
  max-width: 1200px;
  margin: 0 auto;
}

.contact__header {
  text-align: center;
  margin-bottom: 3rem;
}

.contact__label {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #A88A5A;
  margin-bottom: 0.75rem;
}

.contact__title {
  font-size: clamp(1.6rem, 3vw, 2.4rem);
  font-weight: 700;
  color: #2c2c2c;
  margin: 0 0 1rem;
}

.contact__desc {
  color: #777;
  font-size: 1rem;
  max-width: 520px;
  margin: 0 auto;
  line-height: 1.7;
}

.contact__body {
  display: grid;
  grid-template-columns: 1fr 1.4fr;
  gap: 2.5rem;
  align-items: start;
}

.contact__info {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.info__card {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  background: #fff;
  border-radius: 6px;
  padding: 1.25rem 1.5rem;
  box-shadow: 0 1px 6px rgba(0,0,0,0.06);
}

.info__icon {
  flex-shrink: 0;
  width: 42px;
  height: 42px;
  background-color: #F5EDD8;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.info__title {
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: #A88A5A;
  margin: 0 0 0.35rem;
}

.info__text {
  font-size: 0.95rem;
  font-family: sans-serif;
  color: #555;
  line-height: 1.6;
  margin: 0;
}

.info__whatsapp {
  display: inline-block;
  font-size: 0.95rem;
  font-weight: 600;
  color: #25D366;
  text-decoration: none;
  margin-top: 0.1rem;
  transition: opacity 0.2s;
}

.info__whatsapp:hover {
  opacity: 0.75;
}

.contact__map {
  height: 460px;
  border-radius: 6px;
  overflow: hidden;
  box-shadow: 0 1px 6px rgba(0,0,0,0.08);
}

.reviews {
  margin-top: 2.5rem;
}

.reviews__header {
  text-align: center;
  margin-bottom: 1.5rem;
}

.reviews__label {
  display: inline-block;
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  color: #A88A5A;
  margin-bottom: 0.5rem;
}

.reviews__title {
  font-size: clamp(1.2rem, 2.4vw, 1.7rem);
  color: #2c2c2c;
}

.reviews__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.review-card {
  background: #fff;
  border: 1px solid #ece5d8;
  border-radius: 8px;
  padding: 1rem 1.1rem;
  box-shadow: 0 1px 6px rgba(0, 0, 0, 0.04);
}

.review-card__top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.5rem;
  margin-bottom: 0.35rem;
}

.review-card__name {
  font-size: 0.88rem;
  color: #2c2c2c;
}

.review-card__time {
  font-size: 0.75rem;
  color: #8a8a8a;
}

.review-card__stars {
  color: #fbbc04;
  letter-spacing: 1px;
  margin-bottom: 0.55rem;
  font-size: 0.9rem;
}

.review-card__text {
  color: #5c5c5c;
  font-size: 0.9rem;
  line-height: 1.6;
}

.reviews__link {
  display: inline-block;
  margin-top: 1.25rem;
  color: #A88A5A;
  font-weight: 700;
  text-decoration: none;
  border-bottom: 1px solid #A88A5A;
  padding-bottom: 2px;
}

.reviews__link:hover {
  opacity: 0.8;
}

@media (max-width: 860px) {
  .contact__body {
    grid-template-columns: 1fr;
  }

  .contact__map {
    height: 320px;
  }

  .reviews__grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 540px) {
  .contact { padding: 3.5rem 1rem; }
}
</style>
