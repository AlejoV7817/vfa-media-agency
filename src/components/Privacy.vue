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

  <div
    class="overlay"
    @click="closeIfOutside"
  >

    <section class="privacy">

      <!-- BOTÓN CERRAR -->

      <button
        class="close"
        @click="emit('close')"
      >
        ✕
      </button>


      <!-- ENCABEZADO -->

      <p class="updated">
        Última actualización: Septiembre 2026
      </p>

      <h2>
        Política de Privacidad
      </h2>


      <div class="content">

        <!-- INTRODUCCIÓN -->

        <p>
          En <strong>VFA Group</strong> nos comprometemos a proteger
          la información personal de nuestros usuarios, clientes y
          colaboradores, así como a utilizarla de manera responsable
          y transparente.
        </p>


        <p>
          Asimismo, los servicios ofrecidos por <strong>VFA Group</strong>
          se formalizan mediante un contrato o acuerdo entre las partes,
          en el cual se establecen las condiciones, alcances,
          responsabilidades, obligaciones, pagos y demás términos
          correspondientes a cada servicio contratado.
        </p>


        <!-- 1 -->

        <h3>
          1. Responsable del tratamiento
        </h3>

        <p>
          <strong>VFA Group</strong> es responsable del tratamiento
          y protección de los datos personales que sean recabados
          a través de este sitio web, medios de contacto o durante
          la prestación de nuestros servicios.
        </p>


        <!-- 2 -->

        <h3>
          2. Datos personales que podemos recopilar
        </h3>

        <p>
          Podemos recopilar información proporcionada voluntariamente
          por el usuario o cliente, incluyendo nombre, correo electrónico,
          número telefónico, información de contacto y cualquier otro
          dato necesario para atender una solicitud o prestar un servicio.
        </p>


        <!-- 3 -->

        <h3>
          3. Finalidad del uso de la información
        </h3>

        <p>
          Los datos personales podrán utilizarse para:
        </p>

        <p>
          • Atender solicitudes y consultas
          <br>
          • Proporcionar información sobre nuestros servicios
          <br>
          • Elaborar cotizaciones y propuestas
          <br>
          • Dar seguimiento a proyectos
          <br>
          • Formalizar y administrar contratos
          <br>
          • Cumplir con las obligaciones derivadas de los servicios contratados
          <br>
          • Mantener comunicación con clientes y usuarios
          <br>
          • Mejorar nuestros servicios y experiencia de usuario
        </p>


        <!-- 4 -->

        <h3>
          4. Contratación de servicios
        </h3>

        <p>
          La contratación de cualquier servicio ofrecido por
          <strong>VFA Group</strong> podrá estar sujeta a la aceptación
          y firma de un contrato, acuerdo de prestación de servicios
          o documento equivalente.
        </p>

        <p>
          Dicho documento podrá establecer, entre otros aspectos,
          el servicio contratado, alcance del proyecto, entregables,
          tiempos, costos, formas de pago, responsabilidades de las
          partes, condiciones de modificación o cancelación y cualquier
          otra condición aplicable.
        </p>

        <p>
          La prestación del servicio estará sujeta a los términos y
          condiciones establecidos en el acuerdo correspondiente.
        </p>


        <!-- 5 -->

        <h3>
          5. Seguridad de la información
        </h3>

        <p>
          <strong>VFA Group</strong> adopta medidas razonables de
          seguridad para proteger la información personal contra
          acceso no autorizado, pérdida, alteración, divulgación
          o uso indebido.
        </p>


        <!-- 6 -->

        <h3>
          6. Transferencia de datos
        </h3>

        <p>
          No comercializamos ni compartimos los datos personales
          de nuestros usuarios con terceros para fines distintos
          a los informados.
        </p>

        <p>
          En determinados casos, la información podrá ser compartida
          cuando resulte necesario para proporcionar un servicio
          solicitado, cumplir una obligación legal o atender
          requerimientos de las autoridades competentes.
        </p>


        <!-- 7 -->

        <h3>
          7. Cookies y tecnologías similares
        </h3>

        <p>
          Este sitio puede utilizar cookies y tecnologías similares
          para mejorar su funcionamiento, experiencia de navegación
          y, cuando corresponda, analizar el uso del sitio.
        </p>


        <!-- 8 -->

        <h3>
          8. Derechos ARCO
        </h3>

        <p>
          El titular de los datos personales podrá ejercer sus derechos
          de Acceso, Rectificación, Cancelación u Oposición (ARCO),
          de conformidad con la legislación mexicana aplicable.
        </p>

        <p>
          Para realizar una solicitud relacionada con sus datos
          personales, puede comunicarse con nosotros utilizando
          los medios de contacto indicados al final de esta política.
        </p>


        <!-- 9 -->

        <h3>
          9. Conservación de la información
        </h3>

        <p>
          Los datos personales serán conservados durante el tiempo
          necesario para cumplir con las finalidades para las que
          fueron recopilados y, cuando corresponda, durante el periodo
          necesario para cumplir obligaciones legales o contractuales.
        </p>


        <!-- 10 -->

        <h3>
          10. Cambios en la política
        </h3>

        <p>
          <strong>VFA Group</strong> podrá actualizar esta Política
          de Privacidad cuando sea necesario. Cualquier modificación
          será publicada en este sitio y podrá incluir una nueva fecha
          de actualización.
        </p>


        <!-- 11 -->

        <h3>
          11. Contacto
        </h3>

        <p>
          Para cualquier duda, solicitud o asunto relacionado con
          esta Política de Privacidad, puede comunicarse con
          <strong>VFA Group</strong>:
        </p>

        <p>
          <strong>Email:</strong>
          vfagroupp@gmail.com
          <br>

          <strong>Teléfono:</strong>
          +52 55 8778 5216
        </p>

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

  z-index: 3000;

  background: rgba(0, 0, 0, 0.85);

  backdrop-filter: blur(12px);

  display: flex;

  justify-content: center;

  align-items: center;

  animation: fadeIn 0.3s ease;

}


/* ========================================
   CONTENEDOR
======================================== */

.privacy {

  width: 90%;

  max-width: 800px;

  max-height: 85vh;

  overflow-y: auto;

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

  border-radius: 18px;

  padding: 40px;

  color: white;

  position: relative;

  animation: slideUp 0.35s ease;

}


/* ========================================
   BOTÓN
======================================== */

.close {

  position: absolute;

  top: 20px;

  right: 20px;

  width: 38px;

  height: 38px;

  border-radius: 10px;

  border: none;

  cursor: pointer;

  background: rgba(255,255,255,0.05);

  color: white;

  transition: 0.25s;

}


.close:hover {

  background:
    linear-gradient(
      90deg,
      #a855f7,
      #3b82f6
    );

}


/* ========================================
   TITULO
======================================== */

h2 {

  margin-bottom: 10px;

  font-size: 2rem;

}


/* ========================================
   SUBTITULOS
======================================== */

h3 {

  margin-top: 22px;

  margin-bottom: 8px;

  font-size: 1.1rem;

}


/* ========================================
   TEXTO
======================================== */

p {

  color: #9ca3af;

  line-height: 1.6;

}


/* ========================================
   TEXTO DESTACADO
======================================== */

strong {

  color: #e5e7eb;

}


/* ========================================
   ACTUALIZACIÓN
======================================== */

.updated {

  font-size: 0.8rem;

  color: #6b7280;

  margin-bottom: 10px;

}


/* ========================================
   CONTENIDO
======================================== */

.content {

  margin-top: 10px;

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


@keyframes slideUp {

  from {

    opacity: 0;

    transform:
      translateY(40px)
      scale(0.95);

  }

  to {

    opacity: 1;

    transform:
      translateY(0)
      scale(1);

  }

}


/* ========================================
   SCROLLBAR
======================================== */

.privacy::-webkit-scrollbar {

  width: 6px;

}


.privacy::-webkit-scrollbar-thumb {

  background: #a855f7;

  border-radius: 10px;

}


/* ========================================
   MOBILE
======================================== */

@media (max-width: 900px) {

  .overlay {

    align-items: flex-start;

    padding: 40px 10px;

    overflow-y: auto;

  }


  .privacy {

    width: 100%;

    max-height: none;

    padding: 35px 20px;

    margin: 20px 0;

  }


  h2 {

    font-size: 1.7rem;

    padding-right: 40px;

  }


  h3 {

    font-size: 1rem;

  }


  p {

    font-size: 0.92rem;

  }

}

</style>