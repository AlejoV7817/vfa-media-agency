<script setup>

import { ref, onMounted, onBeforeUnmount } from 'vue'

const open = ref(false)

const emit = defineEmits(['open-contact', 'open-privacy'])

const openContact = () => {
  open.value = false
  emit('open-contact')
}

const openPrivacy = () => {
  open.value = false
  emit('open-privacy')
}

/* 🔥 CLICK FUERA DEL MENÚ */
const handleClickOutside = (e) => {
  const menu = document.querySelector('.menu')
  const hamb = document.querySelector('.hamb')

  if (
    open.value &&
    menu &&
    !menu.contains(e.target) &&
    hamb &&
    !hamb.contains(e.target)
  ) {
    open.value = false
  }
}

/* 🔥 ACTIVAR LISTENER */
onMounted(() => {
  document.addEventListener('click', handleClickOutside)
})

/* 🔥 LIMPIAR */
onBeforeUnmount(() => {
  document.removeEventListener('click', handleClickOutside)
})

</script>

<template>
  <header class="nav">
    
    <div class="wrap container-global">

      <!-- MARCA -->
      <div class="brand">
        VFA_Group_Services
      </div>

      <!-- MENU -->
      <nav class="menu" :class="{ show: open }">
        <a href="#">Inicio</a>
        <a href="#nosotros">Nosotros</a>
        <a href="#servicios">Servicios</a>

        <a href="#" @click.prevent="openContact">Contacto</a>

        <a href="#" class="privacy" @click.prevent="openPrivacy">
          Privacidad
        </a>
      </nav>

      <!-- CTA -->
      <a href="#" @click.prevent="openContact" class="cta">
        Contáctanos
      </a>

      <!-- HAMB -->
      <button class="hamb" @click="open = !open">
        ☰
      </button>

    </div>
  </header>
</template>

<style scoped>

/* NAV */
.nav {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;

  background: rgba(6,6,10,0.65);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255,255,255,0.06);
}

/* WRAP */
.wrap {
  height: 70px;
  display: grid;
  grid-template-columns: auto 1fr auto auto;
  align-items: center;
  gap: 30px;
}

/* MARCA */
.brand {
  font-size: 1.1rem;
  font-weight: 600;
  letter-spacing: 1px;

  background: linear-gradient(90deg,#ec4899,#a855f7,#3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* MENU */
.menu {
  display: flex;
  justify-content: center;
  gap: 26px;
}

.menu a {
  font-size: 0.95rem;
  color: #cfcfd4;
  text-decoration: none;
  font-weight: 500;
  position: relative;
  transition: 0.25s;
}

/* HOVER LINE */
.menu a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -6px;
  width: 0%;
  height: 2px;
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  transition: 0.25s;
}

.menu a:hover {
  color: white;
}

.menu a:hover::after {
  width: 100%;
}

/* PRIVACIDAD (más discreto) */
.privacy {
  font-size: 0.8rem;
  color: #9ca3af;
}

.privacy:hover {
  color: #a855f7;
}

/* CTA */
.cta {
  font-size: 0.9rem;
  padding: 10px 18px;
  border-radius: 10px;
  color: white;
  font-weight: 600;
  text-decoration: none;

  background: linear-gradient(90deg,#a855f7,#3b82f6);
  transition: 0.25s;
}

.cta:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(168,85,247,0.3);
}

/* HAMB */
.hamb {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 1.4rem;
}

/* 🔥 MOBILE */
@media (max-width: 900px) {

  /* 🔥 NAVBAR BASE */
  .nav {
    height: 60px;
  }

  .wrap {
    height: 60px;
    display: flex;
    align-items: center; /* 🔥 centra vertical */
    justify-content: space-between;
  }

  .brand {
    font-size: 0.95rem;
  }

  /* 🔥 MENÚ */
  .menu {
    position: absolute;
    top: 65px;
    right: 15px;

    flex-direction: column;
    width: 220px;

    background: rgba(10,10,10,0.95);
    backdrop-filter: blur(10px);

    border-radius: 12px;
    padding: 10px 0;

    display: none;

    box-shadow: 0 10px 30px rgba(0,0,0,0.5);
  }

  .menu.show {
    display: flex;
  }

  .menu a {
    padding: 14px 20px;
    text-align: left;
    font-size: 0.95rem;
  }

  /* 🔥 BOTÓN CTA OCULTO */
  .cta {
    display: none;
  }

  /* 🔥 HAMBURGUESA */
  .hamb {
    display: block;
    font-size: 1.3rem;
  }

}

</style>