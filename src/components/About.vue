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
            ¡Hola! Soy María José, una apasionada de la tecnología y recién graduada en Desarrollo de Aplicaciones
          Multiplataforma.
            <br><br>
             Tras dedicar varios años al cuidado y bienestar animal, decidí dar un salto hacia un sector que me permite
          unir creatividad, lógica y resolución de problemas: el desarrollo de software.
            <br><br>
            Estoy buscando mi primera experiencia profesional en IT, donde pueda seguir creciendo, aportar valor con mis
          conocimientos y aprender nuevas tecnologías.
          </p>

          <h3>Tecnologías utilizadas:</h3>
          <ul>
            <li><strong>Lenguajes de programación:</strong></li>
            <p>Java, JavaScript, Kotlin y Python</p>
            <li><strong>Frameworks y bibliotecas:</strong></li>
            <p>Vue, React, Angular, Spring Boot, Hibernate, Bootstrap, HTML5 y CSS3</p>
            <li><strong>Bases de datos:</strong></li>
            <p>MySQL, MongoDB y PostgreSQL</p>
            <li><strong>Herramientas:</strong></li>
            <p>Vite, Capacitor, Docker, Microsoft Office, Trello, Figma y AWS</p>
            <li><strong>Control de versiones:</strong></li>
            <p>Git, GitHub y GitLab</p>
            <li><strong>Entornos de desarrollo:</strong></li>
            <p>Android Studio, Visual Studio Code, IntelliJ IDEA y Cursor</p>
          </ul>

          <div class="btn-group" data-aos="fade-up" data-aos-delay="400">
            <a class="btn" href="/Portfolio/CV-MariaJose.pdf" target="_blank">Descargar CV</a>
            <a class="btn" href="/Portfolio/Carta de Recomendación.pdf" target="_blank">Carta de Recomendación</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped src="/src/styles/About.css"></style>

<script>
export default {
  name: 'About'
}
</script>