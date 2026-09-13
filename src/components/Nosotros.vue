<script setup>

</script>

<template>

  <section id="nosotros" class="about">

    <div class="container-global">

      <!-- TAG -->
      <p class="tag">SOBRE NOSOTROS</p>

      <!-- TITULO -->
      <h2>
        Creamos oportunidades que <br>
        <span>impulsan nuevas ideas</span>
      </h2>

      <!-- CONTENIDO -->
      <div class="about-content">

        <!-- TEXTO -->
        <div class="text">

          <h3>
            Somos un grupo enfocado en crear,
            desarrollar y hacer crecer proyectos
          </h3>

          <p>
            En <strong>VFA Group</strong> desarrollamos proyectos,
            servicios y soluciones pensados para generar valor,
            nuevas oportunidades y crecimiento.
          </p>

          <p>
            Combinamos creatividad, tecnología, estrategia y
            visión empresarial para convertir ideas en proyectos
            reales, funcionales y con potencial de crecimiento.
          </p>

          <p>
            Nuestra visión es construir diferentes líneas de
            negocio bajo una misma marca, ofreciendo soluciones
            que se adapten a las necesidades de personas,
            emprendedores y empresas.
          </p>

          <p>
            Desde servicios digitales y desarrollo web hasta
            formación, productos y nuevos proyectos comerciales,
            <strong>VFA Group</strong> busca crecer constantemente
            y crear nuevas oportunidades.
          </p>

        </div>

        <!-- CARACTERISTICAS -->
        <div class="features">

          <!-- 1 -->
          <div class="feature">

            <i class="fas fa-lightbulb"></i>

            <div>

              <h4>Ideas y Creatividad</h4>

              <p>
                Convertimos ideas en proyectos con propósito,
                estructura y potencial.
              </p>

            </div>

          </div>


          <!-- 2 -->
          <div class="feature">

            <i class="fas fa-rocket"></i>

            <div>

              <h4>Innovación y Crecimiento</h4>

              <p>
                Buscamos constantemente nuevas formas de
                desarrollar y hacer crecer nuestros proyectos.
              </p>

            </div>

          </div>


          <!-- 3 -->
          <div class="feature">

            <i class="fas fa-layer-group"></i>

            <div>

              <h4>Diversidad de Soluciones</h4>

              <p>
                Desarrollamos servicios, productos y proyectos
                en diferentes áreas y sectores.
              </p>

            </div>

          </div>


          <!-- 4 -->
          <div class="feature">

            <i class="fas fa-handshake"></i>

            <div>

              <h4>Compromiso</h4>

              <p>
                Trabajamos con profesionalismo, responsabilidad
                y visión a largo plazo.
              </p>

            </div>

          </div>


          <!-- 5 -->
          <div class="feature">

            <i class="fas fa-file-signature"></i>

            <div>

              <h4>Servicios por Contrato</h4>

              <p>
                Todos nuestros servicios se formalizan mediante
                contrato, estableciendo claramente las condiciones,
                alcances, responsabilidades y acuerdos entre ambas partes.
              </p>

            </div>

          </div>

        </div>

      </div>

    </div>

  </section>

</template>


<style scoped>

.about {

  padding: 120px 20px;

  color: white;

  background:

    radial-gradient(
      circle at 20% 30%,
      rgba(168,85,247,0.12),
      transparent
    ),

    radial-gradient(
      circle at 80% 70%,
      rgba(59,130,246,0.12),
      transparent
    ),

    #050507;

}


/* TAG */

.tag {

  text-align: center;

  color: #ec4899;

  margin-bottom: 10px;

  font-size: 0.9rem;

}


/* TITULO */

h2 {

  text-align: center;

  font-size: 2.8rem;

  margin-bottom: 70px;

  line-height: 1.3;

}


h2 span {

  background: linear-gradient(
    90deg,
    #a855f7,
    #3b82f6
  );

  -webkit-background-clip: text;

  -webkit-text-fill-color: transparent;

}


/* LAYOUT */

.about-content {

  display: grid;

  grid-template-columns: 1.2fr 1fr;

  gap: 60px;

  align-items: center;

}


/* TEXTO */

.text h3 {

  font-size: 1.6rem;

  margin-bottom: 20px;

}


.text p {

  color: #9ca3af;

  margin-bottom: 15px;

  line-height: 1.6;

}


/* FEATURES */

.features {

  display: flex;

  flex-direction: column;

  gap: 20px;

}


.feature {

  display: flex;

  gap: 15px;

  align-items: flex-start;

  background: rgba(255,255,255,0.02);

  border: 1px solid rgba(255,255,255,0.06);

  padding: 20px;

  border-radius: 12px;

  transition: 0.3s;

}


.feature:hover {

  transform: translateY(-5px);

  border-color: rgba(168,85,247,0.4);

}


/* ICONO */

.feature i {

  font-size: 22px;

  background: linear-gradient(
    90deg,
    #a855f7,
    #3b82f6
  );

  -webkit-background-clip: text;

  -webkit-text-fill-color: transparent;

}


/* TEXTO */

.feature h4 {

  margin-bottom: 5px;

}


.feature p {

  color: #9ca3af;

  font-size: 0.9rem;

}


/* RESPONSIVE */

@media (max-width: 900px) {

  .about {

    padding: 90px 20px;

    text-align: center;

  }


  /* TITULO */

  .about h2 {

    font-size: 1.9rem;

    line-height: 1.2;

    margin-bottom: 20px;

  }


  /* DESCRIPCIÓN */

  .about p {

    font-size: 0.95rem;

    line-height: 1.5;

    max-width: 320px;

    margin: 0 auto 15px;

  }


  /* CONTENIDO PRINCIPAL */

  .about-content {

    display: flex;

    flex-direction: column;

    align-items: center;

    gap: 40px;

  }


  /* TEXTO */

  .text {

    max-width: 320px;

  }


  /* CARDS */

  .features {

    display: flex;

    flex-direction: column;

    gap: 20px;

    width: 100%;

  }


  .feature {

    padding: 20px;

    border-radius: 16px;

    background: rgba(255,255,255,0.03);

    border: 1px solid rgba(255,255,255,0.08);

    text-align: left;

  }

}

</style>