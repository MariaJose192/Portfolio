<template>
    <section class="about-section educacion" data-aos="fade-up" data-aos-delay="100" data-aos-duration="1000">
        <h1 class="about-title" data-aos="fade-right">PROYECTOS</h1>
        <div class="project app-container" v-for="(proyecto, index) in proyectos" :key="proyecto.nombre">
            <div class="image-container" @mousemove="handleMouseMove($event, index)" @mouseleave="resetImage(index)">
                <img :src="proyecto.imagen" :alt="proyecto.nombre" class="project-image" :style="proyecto.style"
                    @click="abrirVisor(proyecto.imagenesExtras, 0)" style="cursor: pointer" />
            </div>
            <div class="body-container">
                <h3>{{ proyecto.nombre }}</h3>
                <p>{{ proyecto.descripcion }}</p>
                <p v-if="proyecto.tecnologias && proyecto.tecnologias.trim() !== ''"><strong>Tecnologías:</strong> {{
                    proyecto.tecnologias }}</p>
                <div>
                    <a v-if="proyecto.link && proyecto.link.trim() !== ''" class="btn" :href="proyecto.link"
                        target="_blank">
                        Ver proyecto
                    </a>
                </div>
            </div>
        </div>

        <div v-if="visorAbierto" class="overlay">
            <div class="visor-contenido">
                <span class="cerrar" @click="cerrarVisor">&times;</span>
                <img :src="imagenesVisor[indiceVisor]" class="visor-imagen" />

                <button class="anterior" @click="anteriorImagen" :disabled="indiceVisor === 0">‹</button>
                <button class="siguiente" @click="siguienteImagen"
                    :disabled="indiceVisor === imagenesVisor.length - 1">›</button>
            </div>
        </div>

    </section>
</template>


<style scoped src="/src/styles/About.css"></style>

<script>
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
                    style: {},
                },
                {

                    imagen: '/Portfolio/img/logoClientList.png',
                    nombre: 'Client List',
                    descripcion: 'Aplicación de gestión de clientes. Esta aplicación permite gestionar los clientes incluidos en una base de datos,' +
                        'con funcionalidades de búsqueda, filtrado y edición de datos.',
                    tecnologias: 'Java, Spring Boot, Angular, MySQL, Postman, Bootstrap e Hibernate',
                    link: 'https://github.com/MariaJose192/ClientList',
                    style: {},
                },
                {
                    imagen: '/Portfolio/img/logoNuda.jpg',
                    nombre: 'NUDA',
                    descripcion: 'En proceso...Tienda de ropa minimalista online, donde podrás encontrar un catalogo de prendas y gestionar su compra.',
                    tecnologias: '',
                    link: '',
                    style: {},
                },
                {
                    imagen: '/Portfolio/img/logoPawCare.png',
                    nombre: 'PawCare',
                    descripcion: 'Proximamente...Control clínico de tu mascota',
                    tecnologias: '',
                    link: '',
                    style: {},
                }
            ],
            visorAbierto: false,
            imagenesVisor: [],
            indiceVisor: 0
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
        abrirVisor(imagenes, index) {
            this.imagenesVisor = imagenes
            this.indiceVisor = index
            this.visorAbierto = true
        },
        cerrarVisor() {
            this.visorAbierto = false
        },
        siguienteImagen() {
            if (this.indiceVisor < this.imagenesVisor.length - 1) {
                this.indiceVisor++
            }
        },
        anteriorImagen() {
            if (this.indiceVisor > 0) {
                this.indiceVisor--
            }
        }
    }
}

</script>