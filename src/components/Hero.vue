<script setup>

import logo from '../assets/logo.png'

</script>


<template>

  <section class="hero">

    <div class="wrap container-global">

      <!-- TEXTO -->

      <div class="text fade-up">

        <h1>
          Un grupo, <br>
          <span>Diferentes oportunidades...</span>
        </h1>


        <p class="desc">
          Creamos, desarrollamos y conectamos proyectos,
          servicios y oportunidades en diferentes sectores.
        </p>


        <div class="actions">

          <!-- WHATSAPP -->

          <a
            href="https://wa.me/525587785216"
            target="_blank"
            rel="noopener noreferrer"
            class="btn primary"
          >
            Contáctanos
          </a>


          <!-- SERVICIOS -->

          <a
            href="#servicios"
            class="btn ghost"
          >
            Ver servicios
          </a>

        </div>


        <!-- STATS -->

        <div class="stats">

          <div>

            <h4>100%</h4>

            <p>Satisfacción</p>

          </div>


          <div>

            <h4>Servicio 24h</h4>

            <p>Disponibles</p>

          </div>


          <div>

            <h4>Respuesta</h4>

            <p>Casi inmediata</p>

          </div>

        </div>

      </div>


      <!-- LOGO + REDES -->

      <div class="visual fade-in">

        <img
          :src="logo"
          alt="VFA Group"
        >


        <p class="social-title">
          REDES
        </p>


        <div class="socials">


          <!-- FACEBOOK -->

          <a
            href="https://www.facebook.com/profile.php?id=61594065642099"
            target="_blank"
            rel="noopener noreferrer"
            class="fb"
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
            class="tt"
            aria-label="TikTok"
          >

            <i class="fab fa-tiktok"></i>

          </a>


          <!-- WHATSAPP -->

          <a
            href="https://wa.me/525587785216"
            target="_blank"
            rel="noopener noreferrer"
            class="wa"
            aria-label="WhatsApp"
          >

            <i class="fab fa-whatsapp"></i>

          </a>


        </div>

      </div>

    </div>


    <!-- WHATSAPP FLOTANTE -->

    <a
      href="https://wa.me/525587785216"
      class="whatsapp-float"
      target="_blank"
      rel="noopener noreferrer"
      aria-label="WhatsApp"
    >

      <i class="fab fa-whatsapp"></i>

    </a>


  </section>

</template>

<style>

/* RESET LINKS */
a {
  text-decoration: none !important;
}

/* HERO */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  color: white;
  background: #050507;
  position: relative;
  overflow: hidden;
}

/* FONDO ANIMADO */
.hero::before {
  content: "";
  position: absolute;
  width: 120%;
  height: 120%;
  top: -10%;
  left: -10%;

  background:
    radial-gradient(circle at 30% 30%, rgba(168,85,247,0.35), transparent 40%),
    radial-gradient(circle at 70% 70%, rgba(59,130,246,0.35), transparent 40%);

  filter: blur(80px);
  animation: moveGlow 10s ease-in-out infinite alternate;
  z-index: 0;
}

.hero::after {
  content: "";
  position: absolute;
  inset: 0;
  background-image: radial-gradient(rgba(255,255,255,0.08) 1px, transparent 1px);
  background-size: 40px 40px;
  animation: moveParticles 20s linear infinite;
  z-index: 0;
}

/* CONTENIDO */
.wrap {
  position: relative;
  z-index: 2;
  display: flex;
  align-items: center;
  justify-content: space-between;
   gap: clamp(40px, 6vw, 80px);
}

/* TEXTO */
.text {
  max-width: 560px;
}

h1 {
  font-size: clamp(2.2rem, 4vw, 3.2rem);
  font-weight: 700;
}

h1 span {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.desc {
  margin-top: 20px;
  color: #9ca3af;
}

/* BOTONES */
.actions {
  margin-top: 30px;
  display: flex;
  gap: 20px;
}

.btn {
  padding: 14px 24px;
  border-radius: 10px;
}

.primary {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  color: white;
}

.ghost {
  border: 1px solid #a855f7;
  color: #a855f7;
}

/* STATS */
.stats {
  display: flex;
  gap: 40px;
  margin-top: 40px;
}

.stats h4 {
  font-size: 1.3rem;
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.stats p {
  font-size: 0.8rem;
  color: #9ca3af;
}

/* VISUAL */
.visual {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.visual img {
  width: clamp(200px, 30vw, 420px);
}

/* REDES */
.social-title {
  font-size: 0.75rem;
  color: #9ca3af;
  margin-top: 10px;
}

.socials {
  display: flex;
  gap: 18px;
  margin-top: 10px;
}

/* BOTONES BASE */
.socials a {
  width: 58px;
  height: 58px;
  border-radius: 16px;

  display: flex;
  align-items: center;
  justify-content: center;

  font-size: 22px;

  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);

  color: #cfcfd4;

  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

/* 🔥 EFECTO GLOW SUAVE */
.socials a::before {
  content: "";
  position: absolute;
  inset: 0;
  opacity: 0;
  transition: 0.3s;
}

/* INSTAGRAM */
.socials a.ig:hover {
  color: white;
  background: linear-gradient(135deg,#E1306C,#833AB4,#405DE6);
  box-shadow: 0 0 25px rgba(225,48,108,0.6);
}

/* TIKTOK */
.socials a.tt:hover {
  color: white;
  background: #000;
  box-shadow: 0 0 25px #25F4EE;
}

/* WHATSAPP */
.socials a.wa {
  background: #25D366;
  color: white;
}

.socials a.wa:hover {
  transform: scale(1.08);
  box-shadow: 0 0 25px #25D366;
}

/* HOVER GENERAL */
.socials a:hover {
  transform: translateY(-6px) scale(1.05);
}

/* FLOAT */
.whatsapp-float {
  position: fixed;
  bottom: 20px;
  right: 20px;

  width: 65px;
  height: 65px;

  border-radius: 50%;
  background: #25D366;

  display: flex;
  align-items: center;
  justify-content: center;

  font-size: 28px;
  color: white;

  box-shadow: 0 10px 30px rgba(37,211,102,0.4);

  z-index: 9999; /* 🔥 CLAVE */

  transition: all 0.3s ease;
}

.whatsapp-float:hover {
  transform: scale(1.1);
  box-shadow: 0 0 30px #25D366;

}

/* ANIMACIONES */
@keyframes moveGlow {
  0% { transform: translate(0,0); }
  100% { transform: translate(60px,-60px); }
}

@keyframes moveParticles {
  from { transform: translateY(0); }
  to { transform: translateY(40px); }
}
/* 🔥 ANIMACIONES (CORRECTAS) */

.fade-up {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeUp 0.9s ease forwards;
}

.fade-in {
  opacity: 0;
  transform: scale(0.95);
  animation: fadeIn 1.1s ease forwards;
}

@keyframes fadeUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeIn {
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* LOGO FLOTANTE */
.visual img {
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
  100% { transform: translateY(0px); }
}
/* 🔥 RESPONSIVE BIEN HECHO */
/* 🔥 RESPONSIVE LIMPIO */
@media (max-width: 768px) {

  .hero {
    padding: 130px 20px 80px; /* 🔥 más aire arriba y abajo */
  }

  .wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 50px; /* 🔥 más separación general */
  }

  /* 🔥 LOGO ARRIBA */
  .visual {
    order: -1;
    margin-bottom: 10px;
  }

  .visual img {
    width: 180px;
    margin-bottom: 20px; /* 🔥 separa del contenido */
  }

  /* 🔥 REDES */
  .social-title {
    margin-bottom: 10px;
  }

  .socials {
    justify-content: center;
    gap: 16px;
    margin-bottom: 20px; /* 🔥 separa del texto */
  }

  .socials a {
    width: 42px;
    height: 42px;
  }

  /* 🔥 TEXTO */
  .text {
    order: 1;
    max-width: 320px;
    margin-top: 10px;
  }

  h1 {
    font-size: 1.8rem;
    line-height: 1.2;
    margin-bottom: 15px;
  }

  .desc {
    font-size: 0.9rem;
    margin-bottom: 25px;
  }

  /* 🔥 BOTONES */
  .actions {
    display: flex;
    flex-direction: column;
    gap: 16px;
    align-items: center;
    margin-top: 10px;
  }

  .btn {
    width: 100%;
    max-width: 240px;
    padding: 12px;
    font-size: 0.85rem;
  }

  /* 🔥 WHATSAPP */
  .whatsapp-float {
    width: 55px;
    height: 55px;
    bottom: 18px;
    right: 18px;
  }
/* FACEBOOK */
.socials a.fb:hover {
  background: #1877F2;
  box-shadow: 0 0 20px #1877F2;
}
}

/* ENTRADA TEXTO */


</style>