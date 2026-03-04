<script setup>
import { ref, onMounted, onUnmounted, nextTick } from 'vue'
import logo from '../assets/logo-pedras.png'

const navLinks = [
  { label: 'Início', href: '#inicio' },
  { label: 'Quem Somos', href: '#quem-somos' },
  { label: 'Produtos', href: '#produtos' },
  { label: 'Ambientes', href: '#ambientes' },
  { label: 'Contato', href: '#contato' },
]

const activeSection = ref('inicio')
const scrolled = ref(false)
const menuOpen = ref(false)

let isClickScrolling = false
let clickScrollTimer = null

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}

function onNavClick(e, href) {
  e.preventDefault()

  // Captura se o menu mobile estava aberto ANTES de fechar
  const wasMenuOpen = menuOpen.value
  menuOpen.value = false
  activeSection.value = href.slice(1)

  isClickScrolling = true
  clearTimeout(clickScrollTimer)
  clickScrollTimer = setTimeout(() => { isClickScrolling = false }, 1400)

  if (href === '#inicio') {
    window.scrollTo({ top: 0, behavior: 'smooth' })
    return
  }

  const target = document.querySelector(href)
  if (!target) return

  // Se o menu mobile estava aberto, espera a animação de fechar (0.4s)
  // antes de rolar — senão o header ainda está alto e o scroll erra
  const delay = wasMenuOpen ? 420 : 0

  setTimeout(() => {
    target.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }, delay)
}

function handleScroll() {
  scrolled.value = window.scrollY > 60

  if (isClickScrolling) return

  const headerEl = document.querySelector('.header')
  const headerHeight = headerEl ? headerEl.offsetHeight : 130

  const sections = navLinks
    .map(link => document.querySelector(link.href))
    .filter(Boolean)

  let current = sections[0]
  for (const section of sections) {
    const top = section.getBoundingClientRect().top
    if (top <= headerHeight + 1) {
      current = section
    }
  }

  if (current) activeSection.value = current.id
}

onMounted(async () => {
  await nextTick()
  handleScroll()
  window.addEventListener('scroll', handleScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header class="header" :class="{ scrolled }">

    <!-- Faixa superior: contato rápido -->
    <div class="header__topbar">
      <!-- Esquerda: números de contato -->
      <div class="topbar__contacts">
        <span class="topbar__item">
          <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="white">
            <path d="M6.6 10.8c1.4 2.8 3.8 5.1 6.6 6.6l2.2-2.2c.3-.3.7-.4 1-.2 1.1.4 2.3.6 3.6.6.6 0 1 .4 1 1V20c0 .6-.4 1-1 1C10.6 21 3 13.4 3 4c0-.6.4-1 1-1h3.5c.6 0 1 .4 1 1 0 1.3.2 2.5.6 3.6.1.3 0 .7-.2 1L6.6 10.8z"/>
          </svg>
          (41) 3256-7078
        </span>
        <span class="topbar__item">
          <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="white">
            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413z"/>
            <path d="M12 0C5.373 0 0 5.373 0 12c0 2.125.557 4.126 1.533 5.862L.057 23.428a.75.75 0 0 0 .921.921l5.666-1.476A11.94 11.94 0 0 0 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.75A9.741 9.741 0 0 1 6.7 20.2l-.387-.232-4.015 1.046 1.065-3.913-.253-.402A9.718 9.718 0 0 1 2.25 12C2.25 6.615 6.615 2.25 12 2.25S21.75 6.615 21.75 12 17.385 21.75 12 21.75z"/>
          </svg>
          (41) 3256-7078
        </span>
      </div>
      <!-- Direita: redes sociais -->
      <div class="topbar__social">
        <a href="#" class="topbar__social-link" aria-label="Facebook">
          <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="white">
            <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/>
          </svg>
        </a>
        <a href="#" class="topbar__social-link" aria-label="Instagram">
          <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect x="2" y="2" width="20" height="20" rx="5" ry="5"/>
            <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/>
            <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/>
          </svg>
        </a>
      </div>
    </div>

    <div class="header__container">
      <a href="#inicio" class="header__logo">
        <img :src="logo" alt="Pedras Boa Vista" class="header__logo-img" />
      </a>

      <!-- Nav desktop -->
      <nav class="header__nav">
        <ul>
          <li v-for="link in navLinks" :key="link.href">
            <a
              :href="link.href"
              :class="{ active: activeSection === link.href.slice(1) }"
              @click="onNavClick($event, link.href)"
            >{{ link.label }}</a>
          </li>
        </ul>
      </nav>

      <!-- Botão hamburguer (mobile) -->
      <button class="header__hamburger" :class="{ open: menuOpen }" @click="toggleMenu" aria-label="Abrir menu">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>

    <!-- Menu mobile -->
    <nav class="header__mobile-nav" :class="{ open: menuOpen }">
      <ul>
        <li v-for="link in navLinks" :key="link.href">
          <a
            :href="link.href"
            :class="{ active: activeSection === link.href.slice(1) }"
            @click="onNavClick($event, link.href)"
          >{{ link.label }}</a>
        </li>
      </ul>
    </nav>

  </header>
</template>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
  background-color: #F5EDD8;
  box-shadow: 0 2px 0 rgba(0,0,0,0);
  transition: box-shadow 0.4s ease;
}

.header.scrolled {
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.10);
}

/* ── Topbar ── */
.header__topbar {
  width: 100%;
  background-color: #A88A5A;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  max-height: 80px;
  overflow: hidden;
  transition: max-height 0.45s ease, padding 0.45s ease, opacity 0.35s ease;
  opacity: 1;
}

.topbar__social {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.topbar__social-link {
  display: flex;
  align-items: center;
  opacity: 0.9;
  transition: opacity 0.2s;
}

.topbar__social-link:hover {
  opacity: 1;
}

.topbar__contacts {
  display: flex;
  align-items: center;
  gap: 1.5rem;
}

.scrolled .header__topbar {
  max-height: 0;
  padding-top: 0;
  padding-bottom: 0;
  opacity: 0;
}

.topbar__item {
  display: flex;
  align-items: center;
  gap: 0.4rem;
  color: #fff;
  font-family: sans-serif;
  font-size: 1.1rem;
  font-weight: 500;
  letter-spacing: 0.5px;
}

/* ── Header principal ── */
.header__container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  overflow: visible;
  transition: height 0.4s ease;
}

.scrolled .header__container {
  height: 68px;
}

.header__logo {
  text-decoration: none;
  display: flex;
  align-items: center;
}

.header__logo-img {
  height: 90px;
  width: auto;
  object-fit: contain;
  transition: height 0.4s ease;
}

.scrolled .header__logo-img {
  height: 58px;
}

/* ── Nav desktop ── */
.header__nav ul {
  list-style: none;
  display: flex;
  gap: 2.5rem;
  margin: 0;
  padding: 0;
}

.header__nav a {
  text-decoration: none;
  color: gray;
  font-family: 'Raleway', sans-serif;
  font-size: 1.0rem;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding-bottom: 4px;
  border-bottom: 2px solid transparent;
  transition: color 0.2s, border-color 0.2s;
}

.header__nav a:hover {
  color: #A88A5A;
}

.header__nav a.active {
  color: #A88A5A;
  border-bottom-color: #A88A5A;
}

/* ── Hamburguer ── */
.header__hamburger {
  display: none;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 6px;
  width: 40px;
  height: 40px;
}

.header__hamburger span {
  display: block;
  width: 26px;
  height: 2px;
  background-color: #5a4a30;
  border-radius: 2px;
  transition: transform 0.3s ease, opacity 0.3s ease;
  transform-origin: center;
}

.header__hamburger.open span:nth-child(1) {
  transform: translateY(7px) rotate(45deg);
}
.header__hamburger.open span:nth-child(2) {
  opacity: 0;
  transform: scaleX(0);
}
.header__hamburger.open span:nth-child(3) {
  transform: translateY(-7px) rotate(-45deg);
}

/* ── Menu mobile ── */
.header__mobile-nav {
  display: none;
  background-color: #F5EDD8;
  overflow: hidden;
  max-height: 0;
  transition: max-height 0.4s ease, padding 0.3s ease;
  padding: 0 2rem;
}

.header__mobile-nav.open {
  max-height: 400px;
  padding: 1rem 2rem 1.5rem;
}

.header__mobile-nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0;
}

.header__mobile-nav li {
  border-bottom: 1px solid rgba(168, 138, 90, 0.2);
}

.header__mobile-nav li:last-child {
  border-bottom: none;
}

.header__mobile-nav a {
  display: block;
  padding: 0.85rem 0;
  text-decoration: none;
  color: gray;
  font-family: 'Raleway', sans-serif;
  font-size: 1rem;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  transition: color 0.2s;
}

.header__mobile-nav a:hover,
.header__mobile-nav a.active {
  color: #A88A5A;
}

/* ── Responsivo ── */
@media (max-width: 768px) {
  .header__nav {
    display: none;
  }

  .header__hamburger {
    display: flex;
  }

  .header__mobile-nav {
    display: block;
  }

  .header__container {
    height: 72px;
    padding: 0 1.25rem;
  }

  .scrolled .header__container {
    height: 60px;
  }

  .header__logo-img {
    height: 58px;
  }

  .scrolled .header__logo-img {
    height: 48px;
  }

  .header__topbar {
    padding: 0.4rem 1.25rem;
  }

  .topbar__item {
    font-size: 0.8rem;
  }

  .topbar__contacts {
    gap: 0.75rem;
  }
}

@media (max-width: 400px) {
  .topbar__contacts .topbar__item:last-child {
    display: none;
  }
}
</style>
