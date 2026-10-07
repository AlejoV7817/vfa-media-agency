<script setup>

import { ref } from 'vue'

const selectedCourse = ref(null)

const showParticularInfo = ref(false)

const WHATSAPP_NUMBER = '525587785216'

const whatsappLink = (message) => {
  return `https://wa.me/${WHATSAPP_NUMBER}?text=${encodeURIComponent(message)}`
}

const openWhatsApp = (message) => {
  window.open(whatsappLink(message), '_blank', 'noopener,noreferrer')
}

const courses = [

  {

    id: 1,

    title: 'Primer Año',

    number: '01',

    startDate: '17 de noviembre de 2026',
    endDate: '21 de enero de 2027',

    description:

      'Programa de acompañamiento académico para estudiantes de primer año de secundaria, diseñado para fortalecer sus bases matemáticas y apoyar su avance escolar.',

    areas: [

      'Geometría básica',

      'Fundamentos algebraicos',

      'Perímetro y área',

      'Estadística',

      'Probabilidad',

      'Relaciones y sistemas'

    ],

    weeks: [

      {

        title: 'Semana 1 — Geometría básica y números',

        classes: [

          'Ángulos',

          'Circunferencia',

          'Conversión de números'

        ]

      },

      {

        title: 'Semana 2 — Fundamentos algebraicos',

        classes: [

          'Desigualdad del triángulo',

          'Ecuación lineal I',

          'Ecuación lineal II'

        ]

      },

      {

        title: 'Semana 3 — Números, círculo y operaciones',

        classes: [

          'El cero y números negativos',

          'El círculo',

          'Suma y multiplicación'

        ]

      },

      {

        title: 'Semana 4 — Figuras geométricas',

        classes: [

          'Figuras básicas',

          'Triángulos',

          'Rectas notables y cuadriláteros'

        ]

      },

      {

        title: 'Semana 5 — Perímetro, área y medición',

        classes: [

          'Perímetro y área I',

          'Perímetro y área II',

          'Circunferencia y medición'

        ]

      },

      {

        title: 'Semana 6 — Operaciones y lenguaje algebraico',

        classes: [

          'Jerarquía de operaciones',

          'Lenguaje algebraico',

          'Medición y cálculo'

        ]

      },

      {

        title: 'Semana 7 — Estadística y análisis de información',

        classes: [

          'Análisis de dispersión de datos',

          'Frecuencias y tendencia central',

          'Obtención de información'

        ]

      },

      {

        title: 'Semana 8 — Representación de datos y operaciones',

        classes: [

          'Representación de información',

          'Operaciones positivas y negativas I',

          'Operaciones positivas y negativas II'

        ]

      },

      {

        title: 'Semana 9 — Porcentajes, probabilidad y conteo',

        classes: [

          'Porcentajes',

          'Probabilidad',

          'Procedimientos de conteo I'

        ]

      },

      {

        title: 'Semana 10 — Conteo, relaciones y sistemas',

        classes: [

          'Procedimientos de conteo II',

          'Relaciones y proporcionalidad',

          'Sistemas de ecuaciones'

        ]

      }

    ]

  },

  {

    id: 2,

    title: 'Segundo Año',

    number: '02',

    startDate: '18 de noviembre de 2026',
    endDate: '24 de enero de 2027',

    description:

      'Programa de acompañamiento académico para estudiantes de segundo año de secundaria, enfocado en fortalecer conocimientos matemáticos y desarrollar herramientas para resolver problemas.',

    areas: [

      'Geometría y álgebra',

      'Desigualdades',

      'Proporcionalidad',

      'Construcciones geométricas',

      'Análisis de datos',

      'Probabilidad'

    ],

    weeks: [

      {

        title: 'Semana 1 — Geometría y álgebra',

        classes: [

          'Construcción de polígonos regulares',

          'Representación algebraica de áreas',

          'Propiedades de los exponentes'

        ]

      },

      {

        title: 'Semana 2 — Desigualdades y sistemas',

        classes: [

          'Desigualdades con expresiones algebraicas',

          'Sistemas de dos ecuaciones lineales I',

          'Sistemas de dos ecuaciones lineales II'

        ]

      },

      {

        title: 'Semana 3 — Proporcionalidad y construcción',

        classes: [

          'Proporcionalidad inversa',

          'Representación de la proporcionalidad inversa',

          'Construcción a escala'

        ]

      },

      {

        title: 'Semana 4 — Construcciones geométricas',

        classes: [

          'Construcción de polígonos',

          'Teselaciones',

          'Construcción de teselaciones'

        ]

      },

      {

        title: 'Semana 5 — Círculos y sistemas de medida',

        classes: [

          'Intersecciones entre círculos y figuras',

          'Áreas mediante intersecciones',

          'Múltiplos y submúltiplos'

        ]

      },

      {

        title: 'Semana 6 — Medición y figuras compuestas',

        classes: [

          'Conversiones entre magnitudes',

          'Perímetro de figuras compuestas',

          'Área de figuras compuestas'

        ]

      },

      {

        title: 'Semana 7 — Análisis de datos',

        classes: [

          'Recolección y registro de datos',

          'Análisis de datos',

          'Medidas de tendencia central'

        ]

      },

      {

        title: 'Semana 8 — Dispersión y tendencias',

        classes: [

          'Medidas de dispersión',

          'Tendencias en los datos',

          'Experimentos aleatorios'

        ]

      },

      {

        title: 'Semana 9 — Probabilidad',

        classes: [

          'Registro de resultados',

          'Medición de probabilidad',

          'Aplicación de la probabilidad'

        ]

      },

      {

        title: 'Semana 10 — Sucesiones cuadráticas',

        classes: [

          'Sucesiones cuadráticas de figuras',

          'Sucesiones cuadráticas de números',

          'Integración y resolución de problemas'

        ]

      }

    ]

  },

  {

    id: 3,

    title: 'Tercer Año',

    number: '03',

    startDate: '17 de noviembre de 2026',
    endDate: '24 de enero de 2027',

    description:

      'Programa de acompañamiento académico para estudiantes de tercer año de secundaria, orientado al fortalecimiento de conocimientos matemáticos y la preparación para los siguientes retos académicos.',

    areas: [

      'Área y volumen',

      'Congruencia y semejanza',

      'Ecuaciones cuadráticas',

      'Teorema de Pitágoras',

      'Trigonometría',

      'Geometría espacial'

    ],

    weeks: [

      {

        title: 'Semana 1 — Área, volumen y congruencia',

        classes: [

          'Área de sólidos geométricos',

          'Volumen de sólidos geométricos',

          'Congruencia de triángulos'

        ]

      },

      {

        title: 'Semana 2 — Semejanza y desarrollos planos',

        classes: [

          'Semejanza de triángulos',

          'Problemas de congruencia y semejanza',

          'Desarrollos planos I'

        ]

      },

      {

        title: 'Semana 3 — Desarrollos y ecuaciones cuadráticas',

        classes: [

          'Desarrollos planos II',

          'Ecuaciones cuadráticas I',

          'Ecuaciones cuadráticas II'

        ]

      },

      {

        title: 'Semana 4 — Factorización y Pitágoras',

        classes: [

          'Ecuaciones cuadráticas III',

          'Teorema de Pitágoras',

          'Aplicación del teorema de Pitágoras'

        ]

      },

      {

        title: 'Semana 5 — Gráficas y variación',

        classes: [

          'Gráficas estadísticas',

          'Variación y representación',

          'Análisis de relaciones'

        ]

      },

      {

        title: 'Semana 6 — Estadística y probabilidad',

        classes: [

          'Análisis estadístico',

          'Medidas y representación',

          'Probabilidad'

        ]

      },

      {

        title: 'Semana 7 — Geometría y volumen',

        classes: [

          'Relaciones geométricas',

          'Cálculo de áreas y volúmenes',

          'Aplicaciones geométricas'

        ]

      },

      {

        title: 'Semana 8 — Álgebra, trigonometría y proporcionalidad',

        classes: [

          'Variables en áreas y volúmenes',

          'Razones trigonométricas',

          'Aplicación de razones trigonométricas'

        ]

      },

      {

        title: 'Semana 9 — Ecuaciones, reparto y sólidos de revolución',

        classes: [

          'Problemas con ecuaciones cuadráticas',

          'Reparto proporcional',

          'Sólidos de revolución'

        ]

      },

      {

        title: 'Semana 10 — Esfera, cono, cilindro y volumen',

        classes: [

          'Relaciones entre esfera, cono y cilindro',

          'Volumen de prismas, pirámides y cilindros',

          'Aplicación y resolución de problemas de volumen'

        ]

      }

    ]

  }

]

const openCourse = (course) => {

  selectedCourse.value = course

}

const closeCourse = () => {

  selectedCourse.value = null

}

const openParticularInfo = () => {

  showParticularInfo.value = true

}

const closeParticularInfo = () => {

  showParticularInfo.value = false

}

</script>

<template>

  <section id="academy" class="academy">

    <div class="academy-container">

      <!-- ================================= -->

      <!-- ENCABEZADO -->

      <!-- ================================= -->

      <div class="academy-header">

        <span class="academy-tag">

          VFA ACADEMY

        </span>

        <h1>

          Apoyo académico para

          <span>secundaria.</span>

        </h1>

        <p>

          Programas diseñados para acompañar el aprendizaje de estudiantes

          de secundaria, con información clara para madres, padres y tutores.

        </p>

      </div>

      <!-- ================================= -->

      <!-- PRECIO PRINCIPAL -->

      <!-- ================================= -->

      <div class="price-highlight">

        <div class="price-content">

          <span class="price-small">

            APRENDIZAJE ACCESIBLE

          </span>

          <h2>

            Desde

            <strong>$60</strong>

            por clase

          </h2>

          <p>

            Accede a un programa estructurado de secundaria con

            <strong>3 clases por semana</strong>,

            durante 10 semanas.

          </p>

        </div>

        <div class="price-details">

          <div>

            <strong>30</strong>

            <span>clases</span>

          </div>

          <div>

            <strong>10</strong>

            <span>semanas</span>

          </div>

          <div>

            <strong>1.5 h</strong>

            <span>por clase</span>

          </div>

        </div>

      </div>

      <!-- ================================= -->

      <!-- MODALIDADES -->

      <!-- ================================= -->

      <div class="modalities">

        <div class="section-title">

          <span>

            ELIGE LA MODALIDAD

          </span>

          <h2>

            Una opción para cada necesidad

          </h2>

          <p>

            Como tutor puedes elegir entre seguir el programa completo,

            adquirir únicamente una semana o solicitar clases particulares.

          </p>

        </div>

        <div class="modality-grid">

          <!-- ================================= -->

          <!-- CURSO COMPLETO -->

          <!-- ================================= -->

          <article class="modality-card featured">

            <div class="featured-label">

              MÁS COMPLETO

            </div>

            <span class="modality-tag">

              PROGRAMA ACADÉMICO

            </span>

            <h3>

              Curso completo

            </h3>

            <!-- PRECIO -->

            <div class="modality-price">

              <div class="price-per-class">

                <strong>

                  $60

                </strong>

                <span>

                  por clase

                </span>

              </div>

              <div class="price-offer">

                <span class="old-price">

                  $2,500

                </span>

                <span class="arrow-price">

                  →

                </span>

                <strong class="final-price">

                  $1,800

                </strong>

              </div>

              <span class="offer-label">

                PAGO ÚNICO POR EL PROGRAMA COMPLETO

              </span>

            </div>

            <p>

              Programa completo de 10 semanas con 30 clases

              organizadas de acuerdo con el año escolar.

            </p>

            <ul>

              <li>

                ✓ 3 clases por semana

              </li>

              <li>

                ✓ 1.5 horas por clase

              </li>

              <li>

                ✓ 10 semanas

              </li>

              <li>

                ✓ 30 clases

              </li>

              <li>

                ✓ Programa completo

              </li>

            </ul>

            <button

              class="modality-button"

              @click="openCourse(courses[0])"

            >

              Ver más información

              <span>→</span>

            </button>

            <button
              class="modality-button whatsapp-button"
              @click="openWhatsApp('Hola, quiero más información sobre el Curso Completo de VFA Academy. Me interesa conocer fechas, horarios y proceso de inscripción.')"
            >
              Enviar mensaje por WhatsApp
              <span>↗</span>
            </button>

          </article>

          <!-- ================================= -->

          <!-- UNA SEMANA -->

          <!-- ================================= -->

          <article class="modality-card">

            <span class="modality-tag">

              FLEXIBLE

            </span>

            <h3>

              Una semana

            </h3>

            <div class="modality-price">

              <div class="price-per-class">

                <strong>

                  $250

                </strong>

                <span>

                  por semana

                </span>

              </div>

            </div>

            <p>

              Ideal para tutores que quieren conocer o trabajar

              únicamente los temas correspondientes a una semana.

            </p>

            <ul>

              <li>

                ✓ Acceso a una semana

              </li>

              <li>

                ✓ Temas correspondientes

              </li>

              <li>

                ✓ Clases de la semana

              </li>

              <li>

                ✓ Sin contratar las 10 semanas

              </li>

            </ul>

            <button

              class="modality-button secondary"

              @click="openCourse(courses[0])"

            >

              Ver más información

              <span>→</span>

            </button>

            <button
              class="modality-button whatsapp-button"
              @click="openWhatsApp('Hola, quiero más información sobre la modalidad de Una Semana de VFA Academy. Me interesa conocer las fechas, temas y cómo puedo inscribirme.')"
            >
              Enviar mensaje por WhatsApp
              <span>↗</span>
            </button>

          </article>

          <!-- ================================= -->

          <!-- CLASES PARTICULARES -->

          <!-- ================================= -->

          <article class="modality-card">

            <span class="modality-tag">

              PERSONALIZADA

            </span>

            <h3>

              Clases particulares

            </h3>

            <div class="modality-price custom">

              <strong>

                Atención individual

              </strong>

            </div>

            <p>

              Una modalidad independiente del programa grupal,

              pensada para estudiantes que necesitan atención

              personalizada en temas específicos.

            </p>

            <ul>

              <li>

                ✓ Atención personalizada

              </li>

              <li>

                ✓ Enfoque en necesidades específicas

              </li>

              <li>

                ✓ Apoyo en temas concretos

              </li>

              <li>

                ✓ Modalidad independiente

              </li>

            </ul>

            <button

              class="modality-button secondary"

              @click="openParticularInfo"

            >

              Ver más información

              <span>→</span>

            </button>

            <button
              class="modality-button whatsapp-button"
              @click="openWhatsApp('Hola, quiero más información sobre las Clases Particulares de VFA Academy. Me interesa conocer disponibilidad, horarios y costo.')"
            >
              Enviar mensaje por WhatsApp
              <span>↗</span>
            </button>

          </article>

        </div>

      </div>

      <!-- ================================= -->

      <!-- MENSAJE PARA TUTORES -->

      <!-- ================================= -->

      <div class="tutor-message">

        <div class="tutor-icon">

          ✓

        </div>

        <div>

          <h2>

            Tú puedes conocer lo que trabajará tu hijo

          </h2>

          <p>

            Consulta el programa correspondiente al año escolar,

            revisa los temas de cada semana y conoce la estructura

            de las clases antes de elegir la modalidad.

          </p>

        </div>

      </div>

      <!-- ================================= -->

      <!-- PROGRAMAS POR AÑO -->

      <!-- ================================= -->

      <div class="programs-title">

        <span>

          PROGRAMAS DE SECUNDARIA

        </span>

        <h2>

          Elige el año escolar

        </h2>

        <p>

          Revisa el contenido académico de cada nivel.

        </p>

      </div>

      <div class="academy-courses">

        <article

          v-for="course in courses"

          :key="course.id"

          class="course-card"

        >

          <div class="course-number">

            {{ course.number }}

          </div>

          <div class="course-content">

            <span class="course-label">

              NIVEL SECUNDARIA

            </span>

            <h2>

              {{ course.title }}

            </h2>

            <p class="course-description">

              {{ course.description }}

            </p>

            <div class="course-meta">

              <span>

                10 semanas

              </span>

              <span>

                30 clases

              </span>

            </div>

            <div class="course-dates">
              <span>Inicio: <strong>{{ course.startDate }}</strong></span>
              <span>Termina: <strong>{{ course.endDate }}</strong></span>
            </div>

            <div class="areas">

              <span

                v-for="area in course.areas"

                :key="area"

              >

                {{ area }}

              </span>

            </div>

            <button

              class="course-button"

              @click="openCourse(course)"

            >

              Ver más información

              <span>

                →

              </span>

            </button>

            <button
              class="course-button whatsapp-button"
              @click="openWhatsApp(`Hola, quiero más información sobre ${course.title} de VFA Academy. Me interesa conocer fechas, horarios y proceso de inscripción.`)"
            >
              Enviar mensaje por WhatsApp
              <span>↗</span>
            </button>

          </div>

        </article>

      </div>

      <!-- ================================= -->

      <!-- PARTE INFERIOR -->

      <!-- ================================= -->

      <div class="academy-bottom">

        <span class="bottom-tag">

          INFORMACIÓN PARA TUTORES

        </span>

        <h2>

          Conoce lo que trabajará tu hijo durante el curso.

        </h2>

        <p>

          Selecciona el año correspondiente para consultar la

          distribución semanal de los temas y las clases.

        </p>

      </div>

    </div>

    <!-- ================================= -->

    <!-- MODAL DEL PROGRAMA -->

    <!-- ================================= -->

    <Transition name="academy-modal">

      <div

        v-if="selectedCourse"

        class="academy-overlay"

        @click.self="closeCourse"

      >

        <div class="program-modal">

          <button

            class="program-close"

            @click="closeCourse"

            aria-label="Cerrar"

          >

            ×

          </button>

          <span class="academy-tag">

            VFA ACADEMY · INFORMACIÓN PARA TUTORES

          </span>

          <h2>

            {{ selectedCourse.title }}

          </h2>

          <p class="modal-subtitle">

            Programa de secundaria · 10 semanas · 30 clases

          </p>

          <div class="modal-dates">
            <span>Inicio: <strong>{{ selectedCourse.startDate }}</strong></span>
            <span>Termina: <strong>{{ selectedCourse.endDate }}</strong></span>
          </div>

          <div class="tutor-modal-info">

            <strong>

              Programa organizado para acompañar el aprendizaje

            </strong>

            <p>

              Consulta los temas correspondientes a cada semana

              y conoce las clases que forman parte del programa.

            </p>

          </div>

          <div class="weeks">

            <div

              v-for="(week, index) in selectedCourse.weeks"

              :key="index"

              class="week"

            >

              <div class="week-number">

                {{ String(index + 1).padStart(2, '0') }}

              </div>

              <div class="week-content">

                <h3>

                  {{ week.title }}

                </h3>

                <ul>

                  <li

                    v-for="(className, classIndex) in week.classes"

                    :key="classIndex"

                  >

                    <span>

                      Clase {{ index * 3 + classIndex + 1 }}

                    </span>

                    {{ className }}

                  </li>

                </ul>

              </div>

            </div>

          </div>


          <button
            class="modality-button modal-whatsapp"
            @click="openWhatsApp(`Hola, quiero más información sobre ${selectedCourse.title} de VFA Academy. Me interesa conocer fechas, horarios, temas y proceso de inscripción.`)"
          >
            Enviar mensaje por WhatsApp
            <span>↗</span>
          </button>
        </div>

      </div>

    </Transition>

    <!-- ================================= -->

    <!-- MODAL PARTICULARES -->

    <!-- ================================= -->

    <Transition name="academy-modal">

      <div

        v-if="showParticularInfo"

        class="academy-overlay"

        @click.self="closeParticularInfo"

      >

        <div class="particular-modal">

          <button

            class="program-close"

            @click="closeParticularInfo"

            aria-label="Cerrar"

          >

            ×

          </button>

          <span class="academy-tag">

            VFA ACADEMY · CLASES PARTICULARES

          </span>

          <h2>

            Atención personalizada

          </h2>

          <p>

            Las clases particulares son una modalidad independiente

            del programa grupal. Están pensadas para estudiantes que

            necesitan apoyo específico en determinados temas.

          </p>

          <div class="particular-box">

            <div>

              <strong>

                Atención individual

              </strong>

              <span>

                Enfoque personalizado

              </span>

            </div>

            <div>

              <strong>

                Temas específicos

              </strong>

              <span>

                Según las necesidades del estudiante

              </span>

            </div>

          </div>

          <button
            class="modality-button whatsapp-button modal-whatsapp"
            @click="openWhatsApp('Hola, quiero más información sobre las Clases Particulares de VFA Academy. Me interesa conocer disponibilidad, horarios y costo.')"
          >
            Enviar mensaje por WhatsApp
            <span>↗</span>
          </button>

          <button
            class="modality-button secondary"
            @click="closeParticularInfo"
          >
            Entendido
          </button>

        </div>

      </div>

    </Transition>

  </section>

</template>

<style scoped>

/* ========================================= */

/* ACADEMY */

/* ========================================= */

.academy {

  position: relative;

  padding: 120px 20px;

  background:

    radial-gradient(

      circle at 15% 20%,

      rgba(168, 85, 247, 0.18),

      transparent 35%

    ),

    radial-gradient(

      circle at 85% 70%,

      rgba(59, 130, 246, 0.18),

      transparent 35%

    ),

    #050507;

  color: #fff;

}

.academy-container {

  width: min(1120px, 100%);

  margin: 0 auto;

}

/* ========================================= */

/* ENCABEZADO */

/* ========================================= */

.academy-header {

  max-width: 820px;

  margin: 0 auto 55px;

  text-align: center;

}

.academy-tag {

  display: inline-block;

  margin-bottom: 18px;

  font-size: 0.85rem;

  font-weight: 700;

  letter-spacing: 2px;

  color: #a855f7;

}

.academy-header h1 {

  margin: 0;

  font-size: clamp(2.5rem, 6vw, 5rem);

  line-height: 1.05;

  font-weight: 800;

  color: #fff;

}

.academy-header h1 span {

  display: block;

  background: linear-gradient(

    90deg,

    #ec4899,

    #a855f7,

    #3b82f6

  );

  -webkit-background-clip: text;

  background-clip: text;

  color: transparent;

}

.academy-header p {

  margin: 28px auto 0;

  max-width: 720px;

  color: #a9a9b5;

  font-size: 1.08rem;

  line-height: 1.7;

}

/* ========================================= */

/* PRECIO PRINCIPAL */

/* ========================================= */

.price-highlight {

  display: flex;

  align-items: center;

  justify-content: space-between;

  gap: 40px;

  margin: 0 auto 80px;

  padding: 35px 40px;

  max-width: 950px;

  border: 1px solid rgba(168,85,247,0.3);

  border-radius: 24px;

  background:

    radial-gradient(

      circle at 10% 20%,

      rgba(236,72,153,0.12),

      transparent 35%

    ),

    rgba(255,255,255,0.035);

  box-shadow:

    0 20px 60px rgba(0,0,0,0.25);

}

.price-small {

  display: block;

  margin-bottom: 8px;

  color: #a855f7;

  font-size: 0.75rem;

  font-weight: 800;

  letter-spacing: 1.5px;

}

.price-content h2 {

  margin: 0;

  color: white;

  font-size: 2rem;

}

.price-content h2 strong {

  font-size: 3.5rem;

  background: linear-gradient(

    90deg,

    #ec4899,

    #a855f7,

    #3b82f6

  );

  -webkit-background-clip: text;

  background-clip: text;

  color: transparent;

}

.price-content p {

  margin: 10px 0 0;

  color: #a9a9b5;

  line-height: 1.6;

}

.price-details {

  display: flex;

  gap: 25px;

}

.price-details div {

  min-width: 75px;

  text-align: center;

}

.price-details strong {

  display: block;

  color: white;

  font-size: 1.5rem;

}

.price-details span {

  color: #92929e;

  font-size: 0.75rem;

}

/* ========================================= */

/* MODALIDADES */

/* ========================================= */

.modalities {

  margin-bottom: 80px;

}

.section-title {

  max-width: 700px;

  margin: 0 auto 35px;

  text-align: center;

}

.section-title > span,

.programs-title > span {

  color: #a855f7;

  font-size: 0.75rem;

  font-weight: 800;

  letter-spacing: 1.5px;

}

.section-title h2,

.programs-title h2 {

  margin: 10px 0;

  color: white;

  font-size: 2.2rem;

}

.section-title p,

.programs-title p {

  color: #92929e;

  line-height: 1.6;

}

.modality-grid {

  display: grid;

  grid-template-columns: repeat(3, 1fr);

  gap: 20px;

}

.modality-card {

  position: relative;

  padding: 30px;

  border: 1px solid rgba(255,255,255,0.08);

  border-radius: 22px;

  background: rgba(255,255,255,0.025);

  transition: 0.3s ease;

}

.modality-card:hover {

  transform: translateY(-6px);

  border-color: rgba(168,85,247,0.4);

  box-shadow:

    0 20px 50px rgba(0,0,0,0.3);

}

.modality-card.featured {

  border-color: rgba(168,85,247,0.45);

  background:

    linear-gradient(

      145deg,

      rgba(168,85,247,0.1),

      rgba(59,130,246,0.04)

    );

}

.featured-label {

  position: absolute;

  top: 0;

  right: 25px;

  padding: 7px 12px;

  border-radius: 0 0 9px 9px;

  background: linear-gradient(

    90deg,

    #ec4899,

    #a855f7

  );

  color: white;

  font-size: 0.65rem;

  font-weight: 800;

  letter-spacing: 1px;

}

.modality-tag {

  color: #a855f7;

  font-size: 0.7rem;

  font-weight: 800;

  letter-spacing: 1.3px;

}

.modality-card h3 {

  margin: 12px 0;

  color: white;

  font-size: 1.6rem;

}

/* ========================================= */

/* PRECIO POR CLASE */

/* ========================================= */

.modality-price {

  margin: 18px 0;

}

.price-per-class {

  display: flex;

  align-items: baseline;

  gap: 8px;

}

.price-per-class strong {

  color: white;

  font-size: 2.8rem;

}

.price-per-class span {

  color: #92929e;

  font-size: 0.9rem;

}

/* ========================================= */

/* PRECIO ANTERIOR + PRECIO FINAL */

/* ========================================= */

.price-offer {

  display: flex;

  align-items: center;

  gap: 10px;

  margin-top: 8px;

}

.old-price {

  color: #777783;

  font-size: 1.05rem;

  text-decoration: line-through;

  text-decoration-thickness: 2px;

}

.arrow-price {

  color: #a855f7;

  font-size: 1rem;

}

.final-price {

  color: #ffffff;

  font-size: 1.55rem;

  font-weight: 800;

  background: linear-gradient(

    90deg,

    #ec4899,

    #a855f7,

    #3b82f6

  );

  -webkit-background-clip: text;

  background-clip: text;

  color: transparent;

}

.offer-label {

  display: block;

  margin-top: 6px;

  color: #92929e;

  font-size: 0.68rem;

  font-weight: 700;

  letter-spacing: 1px;

}

/* PRECIO MODALIDAD SEMANAL */

.modality-price.custom {

  min-height: 48px;

}

.modality-price.custom strong {

  font-size: 1.3rem;

  background: linear-gradient(

    90deg,

    #ec4899,

    #a855f7

  );

  -webkit-background-clip: text;

  background-clip: text;

  color: transparent;

}

/* ========================================= */

/* TEXTO DE TARJETAS */

/* ========================================= */

.modality-card p {

  min-height: 90px;

  color: #a9a9b5;

  line-height: 1.6;

}

.modality-card ul {

  margin: 20px 0 25px;

  padding: 0;

  list-style: none;

}

.modality-card li {

  margin: 10px 0;

  color: #c3c3ce;

  font-size: 0.88rem;

}

/* ========================================= */

/* BOTONES */

/* ========================================= */

.modality-button {

  width: 100%;

  padding: 13px 18px;

  border: none;

  border-radius: 11px;

  color: white;

  background: linear-gradient(

    90deg,

    #a855f7,

    #3b82f6

  );

  font-size: 0.9rem;

  font-weight: 700;

  cursor: pointer;

  transition: 0.25s;

}

.modality-button:hover {

  transform: translateY(-2px);

  box-shadow:

    0 10px 25px rgba(168,85,247,0.25);

}

.modality-button.secondary {

  background: rgba(255,255,255,0.06);

  border: 1px solid rgba(255,255,255,0.1);

}

.modality-button.secondary:hover {

  background: linear-gradient(

    90deg,

    #a855f7,

    #3b82f6

  );

}

/* ========================================= */

/* TUTORES */

/* ========================================= */

.tutor-message {

  display: flex;

  align-items: flex-start;

  gap: 18px;

  max-width: 850px;

  margin: 0 auto 80px;

  padding: 24px 28px;

  border: 1px solid rgba(168,85,247,0.18);

  border-radius: 18px;

  background: rgba(168,85,247,0.06);

}

.tutor-icon {

  flex-shrink: 0;

  width: 42px;

  height: 42px;

  display: grid;

  place-items: center;

  border-radius: 12px;

  background: linear-gradient(

    135deg,

    #a855f7,

    #3b82f6

  );

  color: white;

  font-weight: 800;

  font-size: 1.2rem;

}

.tutor-message h2 {

  margin: 0 0 8px;

  color: #fff;

  font-size: 1.15rem;

}

.tutor-message p {

  margin: 0;

  color: #a9a9b5;

  line-height: 1.6;

}

/* ========================================= */

/* PROGRAMAS */

/* ========================================= */

.programs-title {

  max-width: 700px;

  margin: 0 auto 35px;

  text-align: center;

}

.academy-courses {

  display: grid;

  grid-template-columns: repeat(3, 1fr);

  gap: 24px;

}

.course-card {

  position: relative;

  overflow: hidden;

  padding: 32px;

  border: 1px solid rgba(255,255,255,0.08);

  border-radius: 24px;

  background: rgba(255,255,255,0.025);

  transition: 0.3s ease;

}

.course-card:hover {

  transform: translateY(-8px);

  border-color: rgba(168,85,247,0.45);

  box-shadow:

    0 20px 50px rgba(0,0,0,0.35),

    0 0 40px rgba(168,85,247,0.08);

}

.course-number {

  position: absolute;

  top: -15px;

  right: 10px;

  font-size: 7rem;

  font-weight: 900;

  color: rgba(255,255,255,0.025);

}

.course-content {

  position: relative;

  z-index: 1;

}

.course-label {

  font-size: 0.72rem;

  letter-spacing: 1.5px;

  color: #a855f7;

  font-weight: 700;

}

.course-card h2 {

  margin: 12px 0;

  color: #fff;

  font-size: 2rem;

}

/* =========================================
   FECHAS Y WHATSAPP
   ========================================= */

.course-dates {
  display: flex;
  flex-direction: column;
  gap: 6px;
  margin: 0 0 22px;
  padding: 12px 14px;
  border-radius: 12px;
  background: rgba(168,85,247,0.06);
  border: 1px solid rgba(168,85,247,0.12);
}

.course-dates span {
  color: #92929e;
  font-size: 0.78rem;
  line-height: 1.5;
}

.course-dates strong {
  color: #d8d8e4;
  font-weight: 700;
}

.whatsapp-button {
  margin-top: 10px;
  background: linear-gradient(90deg, #16a34a, #22c55e);
}

.whatsapp-button:hover {
  box-shadow: 0 10px 25px rgba(34,197,94,0.22);
}

.modal-dates {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin: 0 0 25px;
}

.modal-dates span {
  padding: 9px 12px;
  border-radius: 10px;
  background: rgba(168,85,247,0.07);
  border: 1px solid rgba(168,85,247,0.14);
  color: #a9a9b5;
  font-size: 0.8rem;
}

.modal-dates strong {
  color: #e5e5ef;
}

.modal-whatsapp {
  margin-top: 25px;
}

.course-description {

  color: #a9a9b5;

  line-height: 1.6;

  min-height: 115px;

}

.course-meta {

  display: flex;

  gap: 10px;

  margin: 22px 0;

}

.course-meta span {

  padding: 7px 12px;

  border-radius: 20px;

  background: rgba(168,85,247,0.1);

  border: 1px solid rgba(168,85,247,0.18);

  color: #c4b5fd;

  font-size: 0.8rem;

}

.areas {

  display: flex;

  flex-wrap: wrap;

  gap: 8px;

  margin-bottom: 28px;

}

.areas span {

  padding: 6px 10px;

  border-radius: 8px;

  background: rgba(255,255,255,0.045);

  color: #bdbdc8;

  font-size: 0.78rem;

}

.course-button {

  width: 100%;

  padding: 13px 18px;

  border: none;

  border-radius: 11px;

  color: #fff;

  background: linear-gradient(

    90deg,

    #a855f7,

    #3b82f6

  );

  font-size: 0.95rem;

  font-weight: 700;

  cursor: pointer;

  transition: 0.25s;

}

.course-button:hover {

  transform: translateY(-2px);

  box-shadow:

    0 10px 25px rgba(168,85,247,0.25);

}

.course-button span {

  margin-left: 8px;

}

/* ========================================= */

/* PARTE INFERIOR */

/* ========================================= */

.academy-bottom {

  margin: 80px auto 0;

  max-width: 720px;

  text-align: center;

}

.bottom-tag {

  display: inline-block;

  margin-bottom: 10px;

  color: #a855f7;

  font-size: 0.75rem;

  font-weight: 700;

  letter-spacing: 1.5px;

}

.academy-bottom h2 {

  color: #fff;

  font-size: 2rem;

  margin: 0 0 14px;

}

.academy-bottom p {

  color: #92929e;

  line-height: 1.7;

}

/* ========================================= */

/* MODALES */

/* ========================================= */

.academy-overlay {

  position: fixed;

  inset: 0;

  z-index: 3000;

  padding: 30px 20px;

  overflow-y: auto;

  background: rgba(0,0,0,0.82);

  backdrop-filter: blur(14px);

}

.program-modal,

.particular-modal {

  position: relative;

  width: min(900px, 100%);

  margin: 30px auto;

  padding: 45px;

  border: 1px solid rgba(255,255,255,0.09);

  border-radius: 24px;

  background:

    radial-gradient(

      circle at 20% 10%,

      rgba(168,85,247,0.13),

      transparent 35%

    ),

    #090912;

  box-shadow:

    0 30px 80px rgba(0,0,0,0.5);

}

.particular-modal {

  max-width: 600px;

  text-align: center;

}

.particular-modal p {

  color: #a9a9b5;

  line-height: 1.7;

}

.particular-box {

  display: grid;

  grid-template-columns: 1fr 1fr;

  gap: 15px;

  margin: 25px 0;

}

.particular-box div {

  padding: 20px;

  border-radius: 14px;

  background: rgba(255,255,255,0.04);

}

.particular-box strong {

  display: block;

  color: white;

  margin-bottom: 6px;

}

.particular-box span {

  color: #92929e;

  font-size: 0.85rem;

}

.program-modal > h2,

.particular-modal > h2 {

  margin: 0;

  color: #fff;

  font-size: 2.5rem;

}

.modal-subtitle {

  margin: 8px 0 20px;

  color: #9999a8;

}

.tutor-modal-info {

  margin: 0 0 30px;

  padding: 18px 20px;

  border-left: 3px solid #a855f7;

  border-radius: 8px;

  background: rgba(168,85,247,0.06);

  text-align: left;

}

.tutor-modal-info strong {

  display: block;

  margin-bottom: 6px;

  color: #fff;

}

.tutor-modal-info p {

  margin: 0;

  color: #9999a8;

  line-height: 1.6;

}

/* CERRAR */

.program-close {

  position: absolute;

  top: 18px;

  right: 18px;

  width: 42px;

  height: 42px;

  border: 1px solid rgba(255,255,255,0.08);

  border-radius: 10px;

  background: rgba(255,255,255,0.04);

  color: #fff;

  font-size: 26px;

  cursor: pointer;

}

.program-close:hover {

  background: linear-gradient(

    90deg,

    #a855f7,

    #3b82f6

  );

}

/* ========================================= */

/* SEMANAS */

/* ========================================= */

.week {

  display: flex;

  gap: 20px;

  padding: 25px 0;

  border-top: 1px solid rgba(255,255,255,0.07);

}

.week-number {

  min-width: 48px;

  height: 48px;

  display: grid;

  place-items: center;

  border-radius: 12px;

  background: linear-gradient(

    135deg,

    #a855f7,

    #3b82f6

  );

  color: #fff;

  font-weight: 800;

}

.week-content h3 {

  margin: 0 0 15px;

  color: #fff;

  font-size: 1.1rem;

}

.week-content ul {

  margin: 0;

  padding: 0;

  list-style: none;

}

.week-content li {

  margin: 8px 0;

  color: #b9b9c5;

}

.week-content li span {

  display: inline-block;

  min-width: 65px;

  color: #a855f7;

  font-size: 0.8rem;

  font-weight: 700;

}

/* ========================================= */

/* ANIMACIÓN MODAL */

/* ========================================= */

.academy-modal-enter-active,

.academy-modal-leave-active {

  transition: opacity 0.25s ease;

}

.academy-modal-enter-from,

.academy-modal-leave-to {

  opacity: 0;

}

/* ========================================= */

/* MOBILE */

/* ========================================= */

@media (max-width: 900px) {

  .academy {

    padding: 90px 16px;

  }

  .price-highlight {

    flex-direction: column;

    align-items: flex-start;

    padding: 28px;

  }

  .price-content h2 {

    font-size: 1.6rem;

  }

  .price-content h2 strong {

    font-size: 3rem;

  }

  .price-details {

    width: 100%;

    justify-content: space-between;

    gap: 10px;

  }

  .modality-grid {

    grid-template-columns: 1fr;

  }

  .modality-card p {

    min-height: auto;

  }

  .academy-courses {

    grid-template-columns: 1fr;

  }

  .academy-header {

    margin-bottom: 40px;

  }

  .course-card {

    padding: 28px;

  }

  .course-description {

    min-height: auto;

  }

  .tutor-message {

    padding: 20px;

  }

  .program-modal,

  .particular-modal {

    padding: 35px 22px;

  }

  .program-modal > h2,

  .particular-modal > h2 {

    font-size: 2rem;

  }

  .week {

    gap: 12px;

  }

  .week-number {

    min-width: 40px;

    height: 40px;

    font-size: 0.85rem;

  }

  .week-content li span {

    display: block;

    margin-bottom: 3px;

  }

  .particular-box {

    grid-template-columns: 1fr;

  }

  .price-offer {

    flex-wrap: wrap;

  }

}

</style>