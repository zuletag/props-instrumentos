<script>
import CardContent from './components/CardContent.vue';
import Header from './components/Header.vue';
import Instrumento from './components/Instrumento.vue';
import Letras from './components/Letras.vue';
import Numeros from './components/Numeros.vue';

export default {
  components: {
    Header,
    Instrumento,
    CardContent,
    Letras,
    Numeros,
  },

  data() {
    return {
      instrumentos: [
        {
          foto: "https://static.wixstatic.com/media/041826_a1cb3d08b1a743389f60e4aa85e39deb~mv2_d_2028_1790_s_2.png/v1/fill/w_980,h_865,al_c,q_90,usm_0.66_1.00_0.01,enc_auto/041826_a1cb3d08b1a743389f60e4aa85e39deb~mv2_d_2028_1790_s_2.png",
          nombre: "Obobo",
          precio: "$5.769.900",
        },
        {
          foto: "https://www.adagioinstrumentos.cl/wp-content/uploads/2024/03/737-TUBA.jpeg",
          nombre: "Tubaba",
          precio: "$1.490.000",
        },
        {
          foto: "https://www.salaomusical.com/8052-superlarge_default/saxofon-alto-selmer-super-action-80-ii-mi-bemol-dorado-con-estuche.jpg",
          nombre: "Saxomófono",
          precio: "$499.900",
        },
      ],
      imgCard: [
        {
          foto: "https://res.cloudinary.com/practicaldev/image/fetch/s--I4FWon9Y--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ll22z8mea106b4vjdjy7.jpeg",
        }
      ],
      componenteARenderizar: "Letras",
    }
  }
}

</script>

<template>
  <div>
    <Header />
    <div class="instrumentos">
      <div v-for="(instrumento, index) in instrumentos">
        <Instrumento :foto="instrumento.foto" :nombre="instrumento.nombre" :precio="instrumento.precio"
          @eliminarInstrumento="instrumentos.splice(index, 1)">
          <button>Comprar</button>
        </Instrumento>
      </div>
    </div>
    <div class="container">
      <div class="cardDisplay">
        <div class="card" v-for="(img, index) in imgCard">
        <CardContent :foto="img.foto">
          <h1>Title</h1>
          <p>Descripcion</p>
          <button style="margin-bottom: 20px; border-radius: 20px;">Comprar</button>
        </CardContent>
      </div>
      </div>
    </div>
    <div>
      <p>>-----------------------<</p>
      <h3>Componentes Dinamicos</h3>
      <button @click="componenteARenderizar = 'Letras' ">Letras</button>
      <button @click="componenteARenderizar = 'Numeros' ">Numeros</button>
      <div>
        <component :is="componenteARenderizar"></component>
      </div>
    </div>
  </div>
</template>

<style>
.instrumentos {
  width: 80%;
  margin: 30px auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.cardDisplay {
  margin: auto;
  display: flex;
  justify-content: center;
}
</style>
