<template>
  <div class="movie-card">
    <img :src="movie.poster" alt="Movie poster" class="movie-poster" />
    <h2 class="movie-title">{{ movie.title }}</h2>
    <p class="movie-description">{{ movie.description }}</p>
    <button @click="addToFavorites" :class="{ favorite: movie.favorite }" class="favorite-button">
      {{ movie.favorite ? "Remove from favorites" : "Add to favorites" }}
    </button>
  </div>
</template>

<script>
export default {
  props: {
    movie: {
      type: Object,
      required: true,
    },
  },
  methods: {
    addToFavorites() {
      this.movie.favorite = !this.movie.favorite;
    },
  },
};
</script>

<style scoped>
.movie-card {
  border: 1px solid #ccc;
  padding: 1rem;
  margin-bottom: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.movie-poster {
  width: 100%;
  max-width: 200px;
  margin-bottom: 1rem;
}

.movie-title {
  margin: 0;
  margin-bottom: 0.5rem;
}

.movie-description {
  margin: 0;
  margin-bottom: 1rem;
}

.favorite-button {
  background-color: purple;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 0.25rem;
  cursor: pointer;
}

.favorite-button:hover {
  background-color: #8e24aa;
}

.favorite {
  background-color: #8e24aa;
}
</style>