<template>
  <section class="about-section sobre-mi" data-aos="fade-up" data-aos-delay="100" data-aos-duration="1000">
    <div>
      <h1 class="about-title" data-aos="fade-right">SOBRE MÍ</h1>
      <div class="container">
        <div class="image-wrapper" data-aos="zoom-in" data-aos-delay="200" data-aos-duration="1000">
          <img src="/img/portada.jpg" alt="Foto de perfil" style="width: 70%;" />
        </div>
        <div data-aos="fade-up" data-aos-delay="300" data-aos-duration="1000">
          <p>
            ¡Hola! Soy María José,recién graduada en Desarrollo de Aplicaciones
            Multiplataforma.
            <br><br>
            Tras dedicar varios años al cuidado y bienestar animal, decidí dar un salto hacia un sector que me permite
            unir creatividad, lógica y resolución de problemas: el desarrollo de software.
            <br><br>
            Estoy buscando mi primera experiencia profesional en IT, donde pueda seguir creciendo, aportar valor con mis
            conocimientos y aprender nuevas tecnologías.
          </p>

          <h3>Tecnologías utilizadas:</h3>
          <section class="skills">
            <details>
              <summary><strong>Lenguajes de programación:</strong></summary>
              <p>Java</p>
              <p>JavaScript</p>
              <p>Kotlin</p>
              <p>Python</p>
            </details>

            <details>
              <summary><strong>Frameworks y bibliotecas:</strong></summary>
              <p>Vue</p>
              <p>React</p>
              <p>Angular</p>
              <p>Spring Boot</p>
              <p>Hibernate</p>
              <p>Bootstrap</p>
              <p>HTML5</p>
              <p>CSS3</p>
            </details>

            <details>
              <summary><strong>Bases de datos:</strong></summary>
              <p>MySQL</p>
              <p>MongoDB</p>
              <p>PostgreSQL</p>
            </details>

            <details>
              <summary><strong>Herramientas:</strong></summary>
              <p>Vite</p>
              <p>Capacitor</p>
              <p>Docker</p>
              <p>Microsoft Office</p>
              <p>Trello</p>
              <p>Figma</p>
              <p>AWS</p>
            </details>

            <details>
              <summary><strong>Control de versiones:</strong></summary>
              <p>Git</p>
              <p>GitHub</p>
              <p>GitLab</p>
            </details>

            <details>
              <summary><strong>Entornos de desarrollo:</strong></summary>
              <p>Android Studio</p>
              <p>Visual Studio Code</p>
              <p>IntelliJ IDEA</p>
              <p>Cursor</p>

            </details>
          </section>


          <div class="btn-group" data-aos="fade-up" data-aos-delay="400">
            <a class="btn" href="/Portfolio/CV-Maria Jose.pdf" target="_blank">Descargar CV</a>
            <a class="btn" href="/Portfolio/Carta de Recomendación.pdf" target="_blank">Carta de Recomendación</a>
            <a class="btn" @click="showModal = true">Contactar</a>
          </div>
        </div>
      </div>
      
      <div v-if="showModal" class="modal-overlay" @click.self="showModal = false">
        <div class="modal">
          <h2>❤️ Gracias por tu interés en ponerte en contacto conmigo ❤️</h2>
          <p>Correo: <a href="mailto:marialcaraz.192@gmail.com">marialcaraz.192@gmail.com</a></p>
          <p>Teléfono: <a href="tel:+34603521484">603 52 14 84</a></p>
          <button class="btn" @click="showModal = false">Cerrar</button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped src="/src/styles/About.css"></style>

<script>
export default {
  name: 'About',
  data() {
    return {
      showModal: false
    };
  }
}
</script>