<script setup>
import logo from '../assets/logo-pedras.png'
</script>

<template>
  <section id="quem-somos" class="about">
    <div class="about__container">

      <div class="about__logo-col">
        <div class="about__logo-frame">
          <img :src="logo" alt="Pedras Boa Vista" class="about__logo-img" />
        </div>
      </div>

      <div class="about__text">
        <span class="about__label">Quem Somos</span>
        <h2 class="about__title">Tradição e qualidade em pedras naturais</h2>
        <p class="about__description">
          A Pedras Boa Vista nasceu da paixão por transformar ambientes com a beleza única das pedras naturais.
          Há anos no mercado de mármores, granitos e quartzos, oferecemos aos nossos clientes materiais de
          alto padrão aliados a um atendimento personalizado e comprometido com cada detalhe do projeto.
        </p>
        <p class="about__description">
          Trabalhamos com as melhores pedreiras do Brasil e do mundo, garantindo exclusividade,
          durabilidade e o acabamento perfeito que o seu espaço merece. Do planejamento à instalação,
          estamos presentes em cada etapa.
        </p>
        <div class="about__stats">
          <div class="about__stat">
            <strong>+500</strong>
            <span>Projetos entregues</span>
          </div>
          <div class="about__stat">
            <strong>+32</strong>
            <span>Anos de experiência</span>
          </div>
          <div class="about__stat">
            <strong>100%</strong>
            <span>Clientes satisfeitos</span>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 6rem 1.5rem;
  background-color: #fff;
}

.about__container {
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  gap: 5rem;
}

.about__logo-col {
  flex: 0 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
}

.about__logo-frame {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  flex-shrink: 0;
}

.about__logo-img {
  width: 100%;
  height: auto;
  object-fit: contain;
}

.about__text {
  flex: 1;
}

.about__label {
  display: block;
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #A88A5A;
  margin-bottom: 1rem;
}

.about__title {
  font-size: clamp(1.6rem, 3vw, 2.2rem);
  font-weight: 700;
  color: #1C1C1C;
  line-height: 1.3;
  margin-bottom: 1.5rem;
}

.about__description {
  font-size: 1rem;
  color: #666;
  line-height: 1.8;
  margin-bottom: 1rem;
}

.about__stats {
  display: flex;
  gap: 3rem;
  margin-top: 2.5rem;
  padding-top: 2rem;
  border-top: 1px solid #E0CE9E;
}

.about__stat {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.about__stat strong {
  font-size: 1.75rem;
  font-weight: 700;
  color: #A88A5A;
  line-height: 1;
}

.about__stat span {
  font-size: 0.8rem;
  color: #888;
  letter-spacing: 0.5px;
}

@media (max-width: 860px) {
  .about__container {
    flex-direction: column;
    gap: 2.5rem;
    text-align: center;
  }

  .about__stats {
    justify-content: center;
  }
}

@media (max-width: 600px) {
  .about__logo-frame {
    width: 180px;
    height: 180px;
  }

  .about__stats {
    gap: 1.5rem;
    flex-wrap: wrap;
  }
}
</style>
