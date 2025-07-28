<template>
  <div>
    <header>
      <img src="/img/header.png" alt="Foto de perfil" width="100%" />
    </header>
    <main>
      <About />
      <Education />
      <Experience/>
      <Proyects/>
    </main>
    <Contact />
  </div>
</template>

<style scoped src="/src/styles/About.css"></style>

<script>
import Contact from './components/Contact.vue'
import About from './components/About.vue'
import '@fortawesome/fontawesome-free/css/all.min.css'
import AOS from 'aos'
import 'aos/dist/aos.css'
import Education from './components/Education.vue'
import Experience from './components/Experience.vue'
import Proyects from './components/Proyects.vue'

export default {
  mounted() {
    AOS.init()
  },
  components: {
    Contact,
    About,
    Education,
    Experience,
    Proyects
  },
}
</script>
