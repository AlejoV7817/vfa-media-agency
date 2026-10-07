<script setup>
import { ref } from 'vue'

import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Nosotros from './components/Nosotros.vue'
import Services from './components/Services.vue'
import Testimonials from './components/Testimonials.vue'
import Contact from './components/Contact.vue'
import Privacy from './components/Privacy.vue'
import Academy from './components/Academy.vue'


// 🔥 CONTACTO
const showContact = ref(false)

const openContact = () => {
  showContact.value = true
}

const closeContact = () => {
  showContact.value = false
}


// 🔥 PRIVACIDAD
const showPrivacy = ref(false)

const openPrivacy = () => {
  showPrivacy.value = true
}

const closePrivacy = () => {
  showPrivacy.value = false
}


// 🔥 VFA ACADEMY
const openAcademy = () => {
  const academy = document.getElementById('academy')

  if (academy) {
    academy.scrollIntoView({
      behavior: 'smooth',
      block: 'start'
    })
  }
}

</script>


<template>

  <!-- NAVBAR -->
  <Navbar
    @open-contact="openContact"
    @open-privacy="openPrivacy"
    @open-academy="openAcademy"
  />


  <!-- SECCIONES -->
  <Hero />
  <Nosotros />
  <Services />
  <Testimonials />


  <!-- 🔥 VFA ACADEMY -->
  <section id="academy">
    <Academy />
  </section>


  <!-- 🔥 MODALES -->
  <Contact
    v-if="showContact"
    @close="closeContact"
  />

  <Privacy
    v-if="showPrivacy"
    @close="closePrivacy"
  />

</template>


<style>

body {
  margin: 0;
  font-family: 'Inter', sans-serif;
  background: #050507;
}

/* scroll suave */
html {
  scroll-behavior: smooth;
}

/* 🔥 evita que el navbar tape el inicio de Academy */
#academy {
  scroll-margin-top: 80px;
}

</style>