<script setup>
import logo from '../assets/logo-pedras.png'

const navLinks = [
  { label: 'Início', href: '#inicio' },
  { label: 'Quem Somos', href: '#quem-somos' },
  { label: 'Produtos', href: '#produtos' },
  { label: 'Ambientes', href: '#ambientes' },
  { label: 'Contato', href: '#contato' },
]
</script>

<template>
  <footer class="footer">
    <div class="footer__container">

      <div class="footer__col footer__col--brand">
        <a href="#inicio" class="footer__logo-link">
          <img :src="logo" alt="Pedras Boa Vista" class="footer__logo" />
        </a>
        <p class="footer__about">
          Especialistas em pedras naturais para transformar ambientes com beleza, durabilidade e sofisticação.
        </p>
        <div class="footer__social">
          <a href="https://web.facebook.com/pedrasboavista/?locale=pt_BR&_rdc=1&_rdr" class="footer__social-link" aria-label="Facebook">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
              <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/>
            </svg>
          </a>
          <a href="#" class="footer__social-link" aria-label="Instagram">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <rect x="2" y="2" width="20" height="20" rx="5" ry="5"/>
              <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/>
              <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/>
            </svg>
          </a>
          <a href="https://wa.me/554132567078" target="_blank" rel="noopener" class="footer__social-link footer__social-link--wa" aria-label="WhatsApp">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
              <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413z"/>
              <path d="M12 0C5.373 0 0 5.373 0 12c0 2.125.557 4.126 1.533 5.862L.057 23.428a.75.75 0 0 0 .921.921l5.666-1.476A11.94 11.94 0 0 0 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.75A9.741 9.741 0 0 1 6.7 20.2l-.387-.232-4.015 1.046 1.065-3.913-.253-.402A9.718 9.718 0 0 1 2.25 12C2.25 6.615 6.615 2.25 12 2.25S21.75 6.615 21.75 12 17.385 21.75 12 21.75z"/>
            </svg>
          </a>
        </div>
      </div>

      <div class="footer__col">
        <h4 class="footer__heading">Navegação</h4>
        <ul class="footer__nav">
          <li v-for="link in navLinks" :key="link.href">
            <a :href="link.href">{{ link.label }}</a>
          </li>
        </ul>
      </div>

      <div class="footer__col">
        <h4 class="footer__heading">Contato</h4>
        <ul class="footer__info">
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.61 3.36 2 2 0 0 1 3.59 1.18l3-.07a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.75a16 16 0 0 0 5.95 5.95l1.63-1.63a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/>
            </svg>
            (41) 3256-7078
          </li>
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M21 10c0 7-9 13-9 13S3 17 3 10a9 9 0 1 1 18 0z"/>
              <circle cx="12" cy="10" r="3"/>
            </svg>
            Rua João Havro, 1349<br>
            Boa Vista, Curitiba – PR<br>
            CEP 82560-020
          </li>
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="12" r="10"/>
              <polyline points="12 6 12 12 16 14"/>
            </svg>
            Seg – Sex: 08h00 – 12h00<br>
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;13h00 – 18h00
          </li>
        </ul>
      </div>

      <div class="footer__col">
        <h4 class="footer__heading">Formas de Pagamento</h4>
        <div class="footer__payment">


          <div class="payment__card">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 32" width="48" height="32">
              <rect width="48" height="32" rx="4" fill="#1A1F71"/>
              <text x="8" y="22" font-family="Arial" font-size="13" font-weight="bold" font-style="italic" fill="white" letter-spacing="0">VISA</text>
            </svg>
          </div>


          <div class="payment__card">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 32" width="48" height="32">
              <rect width="48" height="32" rx="4" fill="#252525"/>
              <circle cx="18" cy="16" r="9" fill="#EB001B"/>
              <circle cx="30" cy="16" r="9" fill="#F79E1B"/>
              <path d="M24 9.5a9 9 0 0 1 0 13 9 9 0 0 1 0-13z" fill="#FF5F00"/>
            </svg>
          </div>


          <div class="payment__card">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 32" width="48" height="32">
              <rect width="48" height="32" rx="4" fill="#822124"/>
              <text x="5" y="21" font-family="Arial" font-size="8.5" font-weight="bold" fill="white">HIPER</text>
              <text x="5" y="29" font-family="Arial" font-size="5" font-weight="bold" fill="white" letter-spacing="1">CARD</text>
              <circle cx="38" cy="16" r="7" fill="none" stroke="white" stroke-width="2.5"/>
              <circle cx="38" cy="16" r="3" fill="white"/>
            </svg>
          </div>

        </div>
      </div>

    </div>

    <div class="footer__bottom">
      <p>© {{ new Date().getFullYear() }} Pedras Boa Vista. Todos os direitos reservados.</p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: #1c1812;
  color: rgba(255,255,255,0.65);
  font-family: 'Raleway', sans-serif;
}

.footer__container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 4rem 2rem 3rem;
  display: grid;
  grid-template-columns: 1.6fr 1fr 1.4fr 1.2fr;
  gap: 3rem;
}

.footer__col--brand {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.footer__logo-link {
  display: inline-block;
}

.footer__logo {
  height: 70px;
  width: auto;
  object-fit: contain;
}

.footer__about {
  font-size: 0.88rem;
  line-height: 1.75;
  color: rgba(255,255,255,0.5);
  max-width: 260px;
}

.footer__social {
  display: flex;
  gap: 0.75rem;
}

.footer__social-link {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  background: rgba(255,255,255,0.08);
  color: rgba(255,255,255,0.65);
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  transition: background 0.2s, color 0.2s;
}

.footer__social-link:hover {
  background: #A88A5A;
  color: #fff;
}

.footer__social-link--wa:hover {
  background: #25D366;
  color: #fff;
}

.footer__heading {
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  color: #C9A96E;
  margin-bottom: 1.25rem;
}

.footer__nav {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.65rem;
}

.footer__nav a {
  text-decoration: none;
  color: rgba(255,255,255,0.55);
  font-size: 0.9rem;
  transition: color 0.2s;
}

.footer__nav a:hover {
  color: #C9A96E;
}

.footer__info {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.footer__info li {
  display: flex;
  align-items: flex-start;
  gap: 0.6rem;
  font-size: 0.88rem;
  font-family: sans-serif;
  color: rgba(255,255,255,0.55);
  line-height: 1.65;
}

.footer__info svg {
  flex-shrink: 0;
  margin-top: 3px;
  color: #C9A96E;
}

.footer__payment {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.payment__card {
  border-radius: 5px;
  overflow: hidden;
  opacity: 0.85;
  transition: opacity 0.2s;
}

.payment__card:hover {
  opacity: 1;
}

.footer__bottom {
  border-top: 1px solid rgba(255,255,255,0.07);
  text-align: center;
  padding: 1.25rem 2rem;
  font-size: 0.8rem;
  color: rgba(255,255,255,0.3);
}

@media (max-width: 1000px) {
  .footer__container {
    grid-template-columns: 1fr 1fr;
    gap: 2.5rem;
  }
}

@media (max-width: 560px) {
  .footer__container {
    grid-template-columns: 1fr;
    padding: 3rem 1.5rem 2rem;
    gap: 2rem;
  }
}
</style>
