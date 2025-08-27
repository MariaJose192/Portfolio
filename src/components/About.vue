<template>
  <section class="about-section sobre-mi" data-aos="fade-up" data-aos-delay="100" data-aos-duration="1000">
    <div>
      <h1 class="about-title" data-aos="fade-right">SOBRE MÍ</h1>
      <div class="container">
        <div class="image-wrapper" data-aos="zoom-in" data-aos-delay="200" data-aos-duration="1000">
          <img src="/img/portada.jpg" alt="Foto de perfil" style="width: 50%;" />
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
          <section class="skills content">
            <details @toggle="animateDetails($event)">
              <summary>Lenguajes de programación:</summary>
              <div class="accordion-content">
                <p v-for="(item, index) in languages" :key="index" :style="{ transitionDelay: (index * 0.1) + 's' }">
                  {{ item }}
                </p>
              </div>
            </details>

            <details @toggle="animateDetails($event)">
              <summary>Frameworks y bibliotecas:</summary>
              <p v-for="(item, index) in frameworks" :key="index" :style="{ transitionDelay: (index * 0.1) + 's' }">
                {{ item }}
              </p>
            </details>

            <details @toggle="animateDetails($event)">
              <summary>Bases de datos:</summary>
              <p v-for="(item, index) in databases" :key="index" :style="{ transitionDelay: (index * 0.1) + 's' }">
                {{ item }}
              </p>
            </details>

            <details @toggle="animateDetails($event)">
              <summary>Herramientas:</summary>
              <p v-for="(item, index) in tools" :key="index" :style="{ transitionDelay: (index * 0.1) + 's' }">
                {{ item }}
              </p>
            </details>

            <details @toggle="animateDetails($event)">
              <summary>Control de versiones:</summary>
              <p v-for="(item, index) in versionControl" :key="index" :style="{ transitionDelay: (index * 0.1) + 's' }">
                {{ item }}
              </p>
            </details>

            <details @toggle="animateDetails($event)">
              <summary>Frameworks y bibliotecas:</summary>
              <p v-for="(item, index) in ide" :key="index" :style="{ transitionDelay: (index * 0.1) + 's' }">
                {{ item }}
              </p>
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
      
      showModal: false,
      languages: ['Java', 'JavaScript', 'Kotlin', 'Python'],
      frameworks: ['Vue', 'React', 'Angular', 'Spring Boot', 'Hibernate', 'Bootstrap', 'HTML5', 'CSS3'],
      databases: ['MySQL', 'MongoDB', 'PostgreSQL'],
      tools: ['Vite', 'Capacitor', 'Docker', 'Microsoft Office', 'Trello', 'Jira', 'Figma', 'AWS'],
      versionControl: ['Git', 'GitHub', 'GitLab'],
      ide: ['Android Studio', 'Visual Studio Code', 'IntelliJ IDEA', 'Cursor']
    };
  },
  methods: {
    animateDetails(event) {
      const details = event.currentTarget;
      const ps = details.querySelectorAll('p');

      if (!details.open) {
        ps.forEach(p => {
          p.style.opacity = 0;
          p.style.transform = 'translateY(10px)';
        });
        return;
      }

      ps.forEach((p, index) => {
        p.style.transition = 'none';
        p.style.opacity = 0;
        p.style.transform = 'translateY(10px)';

        setTimeout(() => {
          p.style.transition = 'all 0.3s ease';
          p.style.opacity = 1;
          p.style.transform = 'translateY(0)';
        }, index * 100);
      });

    }
  }
}


</script>
