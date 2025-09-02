<template>
    <section class="about-section educacion" data-aos="fade-up" data-aos-delay="100" data-aos-duration="1000">
        <h1 class="about-title" data-aos="fade-right">PROYECTOS</h1>
        <div class="project app-container" v-for="(proyecto, index) in proyectos" :key="proyecto.nombre">
            <div class="image-container" @mousemove="handleMouseMove($event, index)" @mouseleave="resetImage(index)">
                <img :src="proyecto.imagen" :alt="proyecto.nombre" class="project-image" :style="proyecto.style" />
            </div>
            <div class="body-container">
                <h3>{{ proyecto.nombre }}</h3>
                <p>{{ proyecto.descripcion }}</p>
                <p v-if="proyecto.tecnologias && proyecto.tecnologias.trim() !== ''"><strong>Tecnologías:</strong> {{
                    proyecto.tecnologias }}</p>
                <div class="btn-group__video">
                    <div>
                        <a v-if="proyecto.link && proyecto.link.trim() !== ''" class="btn" :href="proyecto.link"
                            target="_blank">
                            Ver proyecto
                        </a>
                    </div>

                    <div v-if="proyecto.video && proyecto.video.trim() !== ''">
                        <button class="btn" @click="abrirVideo(proyecto.video)">
                            Ver video
                        </button>
                    </div>
                </div>

                <div v-if="videoAbierto" class="modal-overlay" @click.self="cerrarVideo">
                    <div class="modal">
                        <video controls autoplay class="project-video">
                            <source :src="videoActual" type="video/mp4" />
                            Tu navegador no soporta videos HTML5.
                        </video>
                        <button class="btn" @click="cerrarVideo">Cerrar</button>
                    </div>
                </div>



            </div>
        </div>


    </section>
</template>


<style scoped src="/src/styles/About.css"></style>

<script>
import cartelera from '/videos/cartelera.mp4'

export default {
    name: 'Proyects',

    data() {
        return {
            proyectos: [
                {
                    imagen: '/Portfolio/img/velvetCinema.jpg',
                    nombre: 'Velvet Cinema',
                    descripcion: 'Aplicación multiplataforma para la gestión de la venta online de entradas de cine.\n' +
                        'Permite a los usuarios comprar entradas, ver horarios, trailer o la información del cine.\n' +
                        'Además, cuenta con un panel de administración para gestionar las películas, horarios y ventas.',
                    tecnologias: 'Java, Spring Boot, React, MySQL, Postman, Capacitor e Hibernate',
                    link: 'https://github.com/MariaJose192/CineVelvet',
                    video: cartelera,
                    mostrarVideo: false


                },
                {

                    imagen: '/Portfolio/img/logoClientList.png',
                    nombre: 'Client List',
                    descripcion: 'Aplicación de gestión de clientes. Esta aplicación permite gestionar los clientes incluidos en una base de datos,' +
                        'con funcionalidades de búsqueda, filtrado y edición de datos.',
                    tecnologias: 'Java, Spring Boot, Angular, MySQL, Postman, Bootstrap e Hibernate',
                    link: 'https://github.com/MariaJose192/ClientList',
                    video: '',
                    mostrarVideo: false


                },
                {
                    imagen: '/Portfolio/img/BodaRD.jpg',
                    nombre: 'La boda de mi amiga',
                    descripcion: 'Web personal para anunciar la boda de mi amiga, con información sobre el evento, ubicación, sugerencias y confirmación de asistencia.',
                    tecnologias: 'Vue, JavaScript, CSS y Tailwind',
                    link: 'https://github.com/MariaJose192/bodaRosaDavid',
                    video: '',
                    mostrarVideo: false


                },
                {
                    imagen: '/Portfolio/img/logoNuda.jpg',
                    nombre: 'NUDA',
                    descripcion: 'En proceso...Tienda de ropa minimalista online, donde podrás encontrar un catálogo de prendas y gestionar su compra.',
                    tecnologias: '',
                    link: '',
                    video: '',
                    mostrarVideo: false


                },
                {
                    imagen: '/Portfolio/img/logoPaw.jpg',
                    nombre: 'Paw Health',
                    descripcion: 'En proceso...Aplicación en la que tendrás acceso a toda la información de tu mascota, recordatorios de vacunas y citas con el veterinario.',
                    tecnologias: '',
                    link: '',
                    video: '',
                    mostrarVideo: false


                }
                
            ],
            videoAbierto: false,
            videoActual: null
        }
    },
    methods: {
        handleMouseMove(event, index) {
            const container = event.currentTarget
            const rect = container.getBoundingClientRect()
            const x = event.clientX - rect.left
            const y = event.clientY - rect.top
            const centerX = rect.width / 2
            const centerY = rect.height / 2
            const rotateX = ((y - centerY) / centerY) * 10
            const rotateY = ((x - centerX) / centerX) * -10

            this.proyectos[index].style = {
                transform: `rotateX(${rotateX}deg) rotateY(${rotateY}deg)`,
                transition: 'transform 0.1s ease'
            }
        },
        resetImage(index) {
            this.proyectos[index].style = {
                transform: 'rotateX(0deg) rotateY(0deg)',
                transition: 'transform 0.3s ease'
            }
        },
        abrirVideo(video) {
            this.videoActual = video
            this.videoAbierto = true
        },
        cerrarVideo() {
            this.videoAbierto = false
            this.videoActual = null
        }
    }
}

</script>