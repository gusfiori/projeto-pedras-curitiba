<template>
  <a
    href="https://wa.me/554132567078"
    target="_blank"
    rel="noopener"
    class="whatsapp-fab"
    aria-label="Falar pelo WhatsApp"
  >
    <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="white">
      <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413z"/>
      <path d="M12 0C5.373 0 0 5.373 0 12c0 2.125.557 4.126 1.533 5.862L.057 23.428a.75.75 0 0 0 .921.921l5.666-1.476A11.94 11.94 0 0 0 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.75A9.741 9.741 0 0 1 6.7 20.2l-.387-.232-4.015 1.046 1.065-3.913-.253-.402A9.718 9.718 0 0 1 2.25 12C2.25 6.615 6.615 2.25 12 2.25S21.75 6.615 21.75 12 17.385 21.75 12 21.75z"/>
    </svg>
    <span class="whatsapp-fab__tooltip">Fale conosco</span>
  </a>
</template>

<style scoped>
.whatsapp-fab {
  position: fixed;
  bottom: 1.75rem;
  right: 1.75rem;
  z-index: 999;
  width: 58px;
  height: 58px;
  background-color: #25D366;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 16px rgba(37, 211, 102, 0.45);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  text-decoration: none;
}

.whatsapp-fab:hover {
  transform: scale(1.1);
  box-shadow: 0 6px 24px rgba(37, 211, 102, 0.55);
}

.whatsapp-fab:hover .whatsapp-fab__tooltip {
  opacity: 1;
  transform: translateX(0);
  pointer-events: auto;
}

.whatsapp-fab__tooltip {
  position: absolute;
  right: calc(100% + 12px);
  background: #1a1a1a;
  color: #fff;
  font-size: 0.78rem;
  font-weight: 600;
  letter-spacing: 0.5px;
  white-space: nowrap;
  padding: 0.4rem 0.85rem;
  border-radius: 4px;
  opacity: 0;
  transform: translateX(6px);
  transition: opacity 0.2s ease, transform 0.2s ease;
  pointer-events: none;
}

.whatsapp-fab__tooltip::after {
  content: '';
  position: absolute;
  top: 50%;
  right: -5px;
  transform: translateY(-50%);
  border: 5px solid transparent;
  border-left-color: #1a1a1a;
  border-right: none;
}
</style>
