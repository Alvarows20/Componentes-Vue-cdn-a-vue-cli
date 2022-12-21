<template>
  <div>
    <header-principal :listHeaders="listHeaders" />
    <div class="d-flex">
      <table>
        <thead>
          <tr class="table-design">
            <th>Película</th>
            <th>Sinopsis</th>
            <th>Categorías</th>
            <th>Calificación</th>
          </tr>
        </thead>
        <tbody>
          <movie-section
            v-for="movie in movieList"
            :key="movie.id"
            :img="movie.img"
            :name="movie.name"
            :category="movie.category"
            :data="movie.data"
            :start="movie.start"
          />
       </tbody>
      </table>
    </div>
    <footer-principal />
  </div>
</template>

<script>
import HeaderPrincipal from "./components/HeaderPrincipal.vue";
import MovieSection from "./components/MovieSection.vue";
import FooterPrincipal from "./components/FooterPrincipal.vue";
export default {
  components: { HeaderPrincipal, MovieSection, FooterPrincipal },
  data() {
    return {
      listHeaders: {
        namePrincipal: "Ejercicio 3 Componentes de VUE CDN a CLI",
        nameAuthor: "Valeria Manríquez A.",
        nameCourse: "Comisión 35960",
      },
      movieList: [
        {
          id: 1,
          img: {
            imagen: "pelicula LADI Di",
            url:
              "https://static.cinepolis.com/img/peliculas/39783/1/1/39783.jpg",
          },
          name: "LADY DI",
          data:
            "The Princess es un documental cargado de emoción sobre la vida y muerte prematura de Diana, la Princesa de Gales, y sus profundas y trascendentales consecuencias. Contada en su totalidad a través de material de archivo.",
          category: "Documental",
          start: 3,
        },
        {
          id: 2,
          img: {
            imagen: "Pelicula erase una vez un genio",
            url:
              "https://static.cinepolis.com/img/peliculas/39969/1/1/39969.jpg",
          },
          name: "Erase una vez un Genio",
          data:
            "La Dra. en literatura Alithea Binnie parece estar feliz con su vida aunque se enfrenta al mundo con cierto escepticismo. De repente, se encuentra con un genio que ofrece concederle tres deseos a cambio de su libertad.",
          category: "Aventura",
          start: 5,
        },
        {
          id: 3,
          img: {
            imagen: "pelicula nop",
            url:
              "https://static.cinepolis.com/img/peliculas/39480/1/1/39480.jpg",
          },
          name: "¡NOP!",
          data:
            "Los cuidadores de un rancho de caballo de California se cruzan con una fuerza misteriosa que afecta no sólo el comportamiento humano sino también el de los animales ¿Estamos presenciando un mal milagro?, ¿Preparados para una nueva experiencia de terror? Nada es lo que parece...",
          category: "Terror",
          start: 2,
        },
      ],
    };
  },
};
</script>
