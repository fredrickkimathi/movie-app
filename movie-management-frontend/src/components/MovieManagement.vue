<template>
  <div class="movie-management">
    <h1 class="title">Fred Movies</h1>
    <input type="text" v-model="searchQuery" placeholder="Search movies..." class="search-input" />
    <div class="movies">
      <movie-card v-for="movie in filteredMovies" :key="movie.id" :movie="movie" @add-to-favorites="addToFavorites" />
    </div>
  </div>
</template>

<script>
import MovieCard from "./MovieCard.vue";

export default {
  components: {
    MovieCard,
  },
  data() {
    return {
      movies: [
        {
          id: 1,
          title: "Once Upon A Time",
          description: "Once upon a time, in a land where the sun painted the skies with hues of gold at dawn and dusk, there existed a kingdom steeped in both magic and mystery. Tucked away amidst rolling hills and dense forests, the kingdom was a realm where every whisper carried a tale, and every shadow held a secret.",
          poster: "./once.jpeg",
          favorite: false,
        },
        {
          id: 2,
          title: "Avengers ENDGAME",
          description: "It is a thrilling culmination of over a decade of Marvel Cinematic Universe storytelling. As the epic conclusion to the Infinity Saga, the film follows Earth's mightiest heroes as they grapple with the aftermath of Avengers: Infinity War, where the villainous Thanos succeeded in wiping out half of all life in the universe.",
          poster: "./avengers.jpg",
          favorite: false,
        },
      ],
      searchQuery: "",
    };
  },
  computed: {
    filteredMovies() {
      return this.movies.filter((movie) => movie.title.toLowerCase().includes(this.searchQuery.toLowerCase()));
    },
  },
  methods: {
    addToFavorites(movie) {
      movie.favorite = !movie.favorite;
    },
  },
};
</script>

<style scoped>
.movie-management {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.title {
  margin-bottom: 1rem;
}

.search-input {
  border: 1px solid #ccc;
  padding: 0.5rem;
  margin-bottom: 1rem;
}

.movies {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>