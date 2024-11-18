<template>
  <div class="gallery">
    <h1>IV Región de Coquimbo</h1>
    <h2>Lugares a visitar:</h2>
    <div class="image-scroll">
      <div v-for="(photo, index) in photos" :key="index" class="image-item">
        <img :src="photo.url" @click="selectImage(photo)" :alt="photo.description" />
      </div>
    </div>
    <ImageDescription v-if="selectedImage" :photo="selectedImage" @close="selectedImage = null" />
  </div>
</template>

<script>
import ImageDescription from './ImageDescription.vue';

export default {
    name: 'ImageGallery',
    // props: {},
    data() {
        return {
            photos: [
                { url: "https://chileestuyo.cl/wp-content/uploads/2019/08/Mamalluca.jpg", author: "Creative Commons", title: "Observatorio Mamalluca", description: "Descubre los secretos del universo en Mamalluca. Sumérgete en una experiencia astronómica inolvidable. Con potentes telescopios, guías expertos y cielos cristalinos, podrás observar planetas, estrellas y galaxias como nunca antes. ¡Un viaje a través del cosmos te espera!" },
                { url: "https://infogate.cl/wp-content/uploads/2017/07/turismo060701.jpg", author: "Creative Commons", title: "Parque Nacional Fray Jorge", description: "Un oasis en el desierto. Explora un bosque milenario que desafía las condiciones áridas del norte de Chile. Caminatas por senderos rodeados de una exuberante vegetación, observación de aves y la magia de un microclima único te esperan en Fray Jorge." },
                { url: "https://chileestuyo.cl/wp-content/uploads/2015/07/Valle-del-Elqui-1.jpg", author: "Creative Commons", title: "Valle del Elqui", description: "El corazón místico de Chile. Conéctate con la naturaleza y la espiritualidad en el Valle del Elqui. Relájate en termas naturales, observa el cielo nocturno más limpio del mundo, degusta piscos artesanales y descubre la cultura ancestral de los pueblos originarios." },
                { url: "https://portaldeelqui.com/storage/galerias/Pe7smv6W2NgxeOviAVPrW0AuIu0VJ8fl78N/thumbs/full-size.jpg", author: "Creative Common", title: "Totoralillo", description: "Paraíso costero para todos los gustos. Disfruta de playas vírgenes, aguas cristalinas y una rica vida marina. Practica surf, buceo, pesca o simplemente relájate bajo el sol. Totoralillo es el destino perfecto para los amantes de la naturaleza y los deportes acuáticos." },
            ],
            selectedImage: null,
        }
    },
    // computed: {},
    methods: {    
      selectImage(photo) {
        this.selectedImage = photo;
      },
    },
    // watch: {},
    components: {
        ImageDescription,
    },
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
};
</script>

<style scoped>
h1 {
  text-align: left;
}
.gallery {
  text-align: center;
}
.image-scroll {
  display: flex;
  flex-direction: column; /* cambia la dirección del flujo a vertical */
  overflow-y: scroll; /* habilita el scroll vertical */
  max-width: 100%;
  max-height: 500px;
  gap: 10px;
  padding: 10px;
  scroll-snap-type: y mandatory; /* Activa el desplazamiento suave en eje vertical */
  scrollbar-width: thin; /* Estiliza el scroll en navegadores modernos */
  scrollbar-color: #aaa #f0f0f0; /* Color del scroll */
}
.image-item {
  flex: 0 0 50%; /* Ocupa el 50% del contenedor, es decir, 2 imágenes visibles */
  margin: 0 10px;
  scroll-snap-align: start; /* Ajusta la imagen al principio al hacer scroll */
}
.image-item img {
  width: 100%;
  height: 60%;
  cursor: pointer;
  transition: transform 0.3s;
}
.image-item img:hover {
  transform: scale(1.1);
}
/* Estiliza el scroll en navegadores WebKit (Chrome, Safari, Edge moderno) */
.image-scroll::-webkit-scrollbar {
  width: 10px; /* Ancho del scroll */
}
.image-scroll::-webkit-scrollbar-thumb {
  background-color: #aaa; /* Color del indicador del scroll */
  border-radius: 5px; /* Bordes redondeados */
}
.image-scroll::-webkit-scrollbar-track {
  background-color: #f0f0f0; /* Fondo del scroll */
}
/* Media Queries para pantallas grandes (desktop) */
@media (min-width: 1024px) {
  .image-scroll {
    max-height: 600px; /* 40%; */
    /* max-width: 80%; */
    gap: 15px;
  }

  .image-item img {
    /*flex: 0 0 45%;*/
    width: 800px;
    height: 400px;
    text-align: center;
  }
}
</style>