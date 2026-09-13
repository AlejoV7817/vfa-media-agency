<script setup>
import { ref, watch } from 'vue'

const current = ref(0)
const showAll = ref(false)
const animate = ref(true)

const reviews = [
  { text: "Excelente servicio. Mi página ahora genera clientes todos los días.", name: "Carlos Méndez", role: "Negocio local" },
  { text: "Diseño moderno y profesional. Superaron mis expectativas.", name: "Andrea López", role: "Emprendedora" },
  { text: "Soporte técnico increíble. Todo rápido y eficiente.", name: "Luis Herrera", role: "Empresa" },
  { text: "Aumenté mis ventas gracias a su marketing digital.", name: "Fernando Ruiz", role: "E-commerce" },
  { text: "Muy buena atención y resultados reales.", name: "Daniel Torres", role: "Freelancer" },
  { text: "Mi negocio ahora se ve profesional en internet.", name: "Sofía Ramos", role: "Tienda online" },
  { text: "El SEO funcionó, ahora aparezco en Google.", name: "Ricardo Vega", role: "Servicios" },
  { text: "Muy recomendados, calidad y atención excelente.", name: "Laura Jiménez", role: "Empresa local" }
]

function next() {
  animate.value = false
  setTimeout(() => {
    current.value = (current.value + 1) % reviews.length
    animate.value = true
  }, 150)
}

function prev() {
  animate.value = false
  setTimeout(() => {
    current.value = (current.value - 1 + reviews.length) % reviews.length
    animate.value = true
  }, 150)
}
</script>

<template>
  <section class="testimonials">

    <div class="container-global">

      <h2 class="fade">Lo que nuestros clientes dicen</h2>

      <!-- SLIDER -->
      <div class="slider" v-if="!showAll">

        <button class="nav-btn left" @click="prev">‹</button>

        <div :class="['review-box', animate ? 'fade' : '']">
          <p class="text">“{{ reviews[current].text }}”</p>
          <h3>{{ reviews[current].name }}</h3>
          <span>{{ reviews[current].role }}</span>
        </div>

        <button class="nav-btn right" @click="next">›</button>

      </div>

      <!-- GRID -->
      <div v-else class="all-reviews fade">
        <div class="review-card" v-for="(r, i) in reviews" :key="i">
          <p>“{{ r.text }}”</p>
          <h4>{{ r.name }}</h4>
          <span>{{ r.role }}</span>
        </div>
      </div>

      <!-- BOTÓN -->
      <div class="actions center">
        <button class="btn" @click="showAll = !showAll">
          {{ showAll ? 'Volver' : 'Ver todos los comentarios' }}
        </button>
      </div>

    </div>

  </section>
</template>

<style>

/* 🔥 BACKGROUND */
.testimonials {
  padding: 120px 20px;
  text-align: center;
  color: white;

  background:
    radial-gradient(circle at 20% 30%, rgba(168,85,247,0.15), transparent),
    radial-gradient(circle at 80% 70%, rgba(59,130,246,0.15), transparent),
    #07070b;
}

/* TITULO */
h2 {
  font-size: 2.6rem;
  margin-bottom: 60px;
}

/* 🔥 ANIMACIÓN SUAVE */
.fade {
  animation: fadeIn 0.5s ease;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(15px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* SLIDER */
.slider {
  position: relative;
  max-width: 650px;
  margin: auto;
}

/* CAJA */
.review-box {
  padding: 45px 35px;
  border-radius: 22px;

  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.1);

  backdrop-filter: blur(12px);

  transition: 0.3s;
}

.review-box:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 50px rgba(168,85,247,0.2);
}

/* TEXTO */
.text {
  font-size: 1.3rem;
  color: #e5e7eb;
  margin-bottom: 20px;
}

h3 {
  font-size: 1.2rem;
  margin-bottom: 5px;
}

span {
  color: #9ca3af;
}

/* FLECHAS */
.nav-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);

  width: 44px;
  height: 44px;

  border-radius: 50%;
  border: 1px solid rgba(255,255,255,0.1);

  background: rgba(255,255,255,0.05);
  color: white;

  cursor: pointer;
  transition: 0.3s;
}

.nav-btn:hover {
  background: linear-gradient(135deg,#a855f7,#3b82f6);
  transform: translateY(-50%) scale(1.1);
}

.left { left: -55px; }
.right { right: -55px; }

/* GRID */
.all-reviews {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  max-width: 1100px;
  margin: auto;
}

.review-card {
  padding: 20px;
  border-radius: 14px;

  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.08);

  transition: 0.3s;
}

.review-card:hover {
  transform: translateY(-5px);
  border-color: rgba(168,85,247,0.4);
}

/* BOTÓN */
.actions.center {
  margin-top: 60px;
  display: flex;
  justify-content: center;
}

.btn {
  padding: 14px 28px;
  border-radius: 10px;

  background: linear-gradient(90deg,#a855f7,#3b82f6);
  color: white;
  border: none;

  cursor: pointer;
  transition: 0.3s;
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(168,85,247,0.3);
}

/* MOBILE */
@media (max-width: 900px) {

  h2 {
    font-size: 1.9rem;
  }

  .review-box {
    padding: 25px;
  }

  .text {
    font-size: 1rem;
  }

  .all-reviews {
    grid-template-columns: 1fr;
  }

  .nav-btn {
    display: none;
  }
}
</style>