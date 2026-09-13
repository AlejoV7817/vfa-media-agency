<script setup>

import { onMounted, onUnmounted } from 'vue'

const emit = defineEmits(['close'])

// Cerrar con ESC
const handleKey = (e) => {

  if (e.key === 'Escape') {
    emit('close')
  }

}

onMounted(() => {

  window.addEventListener('keydown', handleKey)

})

onUnmounted(() => {

  window.removeEventListener('keydown', handleKey)

})

// Click fuera del contenido
const closeIfOutside = (e) => {

  if (e.target.classList.contains('overlay')) {
    emit('close')
  }

}

</script>


<template>

  <!-- OVERLAY -->

  <div
    class="overlay"
    @click="closeIfOutside"
  >

    <section class="contact">

      <!-- BOTÓN CERRAR -->

      <button
        class="close"
        @click="emit('close')"
      >
        ✕
      </button>


      <!-- TAG -->

      <p class="tag">
        CONTACTO
      </p>


      <!-- TITULO -->

      <h2>
        Hablemos sobre tu
        <span>proyecto</span>
      </h2>


      <!-- DESCRIPCIÓN -->

      <p class="desc">
        Estamos listos para ayudarte a convertir tus ideas
        en proyectos y oportunidades.
      </p>


      <!-- GRID -->

      <div class="contact-grid">


        <!-- EMAIL -->

        <a
          href="mailto:vfagroupp@gmail.com"
          class="contact-card"
        >

          <i class="fas fa-envelope"></i>

          <h3>
            Email
          </h3>

          <p>
            vfagroupp@gmail.com
          </p>

        </a>


        <!-- WHATSAPP -->

        <a
          href="https://wa.me/525587785216?text=Hola,%20quiero%20información%20sobre%20sus%20servicios"
          target="_blank"
          rel="noopener noreferrer"
          class="contact-card"
        >

          <i class="fab fa-whatsapp"></i>

          <h3>
            WhatsApp
          </h3>

          <p>
            +52 55 8778 5216
          </p>

        </a>


        <!-- REDES -->

        <div class="contact-card social">

          <i class="fas fa-share-alt"></i>

          <h3>
            Redes
          </h3>


          <div class="social-links">


            <!-- FACEBOOK -->

            <a
              href="https://www.facebook.com/profile.php?id=61594065642099"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="Facebook"
            >

              <i class="fab fa-facebook-f"></i>

            </a>


            <!-- INSTAGRAM -->

            <a
              href="https://www.instagram.com/vfa_group?stkn=ZWVlNnZ6N3VmNnRk&utm_source=qr"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="Instagram"
            >

              <i class="fab fa-instagram"></i>

            </a>


            <!-- TIKTOK -->

            <a
              href="https://www.tiktok.com/@vfa_group"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="TikTok"
            >

              <i class="fab fa-tiktok"></i>

            </a>


            <!-- WHATSAPP -->

            <a
              href="https://wa.me/525587785216"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="WhatsApp"
            >

              <i class="fab fa-whatsapp"></i>

            </a>


          </div>

        </div>


      </div>

    </section>

  </div>

</template>


<style scoped>


/* ========================================
   OVERLAY
======================================== */

.overlay {

  position: fixed;

  inset: 0;

  z-index: 9999;

  background: rgba(0, 0, 0, 0.88);

  backdrop-filter: blur(12px);

  overflow-y: scroll !important;

  overflow-x: hidden !important;

  -webkit-overflow-scrolling: touch;

  touch-action: pan-y;

  display: block;

  padding: 90px 16px 40px;

  animation: fadeIn 0.3s ease;

}


/* OCULTAR SCROLLBAR */

.overlay::-webkit-scrollbar {

  width: 0;

}


/* ========================================
   CONTENIDO
======================================== */

.contact {

  width: 100%;

  max-width: 900px;

  margin: auto;

  padding: 45px 20px;

  border-radius: 26px;

  text-align: center;

  color: white;

  background:

    radial-gradient(
      circle at 20% 30%,
      rgba(168, 85, 247, 0.15),
      transparent
    ),

    radial-gradient(
      circle at 80% 70%,
      rgba(59, 130, 246, 0.15),
      transparent
    ),

    #06060a;

  position: relative;

  min-height: auto !important;

  animation: scaleIn 0.3s ease;

}


/* ========================================
   BOTÓN CERRAR
======================================== */

.close {

  position: absolute;

  top: 20px;

  right: 20px;

  background: rgba(255, 255, 255, 0.08);

  border: none;

  color: white;

  width: 42px;

  height: 42px;

  border-radius: 12px;

  font-size: 20px;

  display: flex;

  align-items: center;

  justify-content: center;

  cursor: pointer;

  z-index: 99999;

  transition: 0.25s;

}


.close:hover {

  background:
    linear-gradient(
      90deg,
      #a855f7,
      #3b82f6
    );

  transform: rotate(90deg);

}


/* ========================================
   TITULO
======================================== */

h2 {

  font-size: 3rem;

  line-height: 1.05;

  margin-bottom: 20px;

}


h2 span {

  background:
    linear-gradient(
      90deg,
      #a855f7,
      #3b82f6
    );

  -webkit-background-clip: text;

  -webkit-text-fill-color: transparent;

}


/* ========================================
   TAG
======================================== */

.tag {

  color: #ec4899;

  margin-bottom: 10px;

  letter-spacing: 2px;

}


/* ========================================
   DESCRIPCIÓN
======================================== */

.desc {

  color: #9ca3af;

  margin-bottom: 45px;

  line-height: 1.7;

  font-size: 1rem;

}


/* ========================================
   GRID
======================================== */

.contact-grid {

  display: grid;

  grid-template-columns:
    repeat(3, 1fr);

  gap: 22px;

}


/* ========================================
   CARDS
======================================== */

.contact-card {

  background:
    rgba(255, 255, 255, 0.03);

  border:
    1px solid
    rgba(255, 255, 255, 0.08);

  padding: 30px 20px;

  border-radius: 20px;

  text-decoration: none;

  color: white;

  transition: 0.3s;

}


.contact-card:hover {

  transform: translateY(-6px);

  border-color:
    rgba(168, 85, 247, 0.5);

  box-shadow:
    0 12px 30px
    rgba(168, 85, 247, 0.25);

}


/* ========================================
   ICONOS
======================================== */

.contact-card > i {

  font-size: 32px;

  margin-bottom: 16px;

  background:
    linear-gradient(
      90deg,
      #a855f7,
      #3b82f6
    );

  -webkit-background-clip: text;

  -webkit-text-fill-color: transparent;

}


/* ========================================
   TITULOS DE CARDS
======================================== */

.contact-card h3 {

  font-size: 1.6rem;

  margin-bottom: 12px;

}


/* ========================================
   TEXTO DE CARDS
======================================== */

.contact-card p {

  color: #d1d5db;

  line-height: 1.6;

  font-size: 1rem;

}


/* ========================================
   REDES
======================================== */

.social-links {

  display: flex;

  justify-content: center;

  gap: 14px;

  margin-top: 20px;

  flex-wrap: wrap;

}


/* BOTONES DE REDES */

.social-links a {

  width: 52px;

  height: 52px;

  border-radius: 14px;

  display: flex;

  align-items: center;

  justify-content: center;

  font-size: 22px;

  background:
    rgba(255, 255, 255, 0.05);

  border:
    1px solid
    rgba(255, 255, 255, 0.08);

  transition: 0.25s;

}


/* ICONOS DE REDES */

.social-links a i {

  margin: 0;

  font-size: 22px;

  background:
    linear-gradient(
      90deg,
      #a855f7,
      #3b82f6
    );

  -webkit-background-clip: text;

  -webkit-text-fill-color: transparent;

}


/* HOVER REDES */

.social-links a:hover {

  transform: translateY(-4px);

  background:
    linear-gradient(
      90deg,
      #a855f7,
      #3b82f6
    );

}


/* AL PASAR EL MOUSE EL ICONO SE VUELVE BLANCO */

.social-links a:hover i {

  background: none;

  -webkit-text-fill-color: white;

  color: white;

}


/* ========================================
   ANIMACIONES
======================================== */

@keyframes fadeIn {

  from {

    opacity: 0;

  }

  to {

    opacity: 1;

  }

}


@keyframes scaleIn {

  from {

    opacity: 0;

    transform: scale(0.94);

  }

  to {

    opacity: 1;

    transform: scale(1);

  }

}


/* ========================================
   MOBILE
======================================== */

@media (max-width: 900px) {

  .overlay {

    padding:
      80px
      14px
      120px;

  }


  .contact {

    padding:
      40px
      18px;

  }


  .contact-grid {

    grid-template-columns: 1fr;

  }


  h2 {

    font-size: 2.5rem;

  }


  .desc {

    font-size: 0.95rem;

  }


  .contact-card {

    padding:
      28px
      18px;

  }

}


/* ========================================
   IPHONE
======================================== */

@supports (-webkit-touch-callout: none) {

  .overlay {

    min-height: 100dvh;

    height: auto;

  }

}

</style>