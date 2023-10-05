<template>
  <div class="character-gallery">
    <CharacterCard 
      v-for="character in characters" 
      :key="character.id" 
      :character="character"
    />
  </div>
</template>

<script>
import axios from 'axios';
import CharacterCard from './CharacterCard.vue'

export default {
  components: {
    CharacterCard
  },
  data() {
    return {
      characters: [],
      currentPage: 1,
      totalPages: null
    };
  },
  methods: {
    async getCharacters() {
      const response = await axios.get(`https://rickandmortyapi.com/api/character?page=${this.currentPage}`);
      this.totalPages = response.data.info.pages;
      this.characters.push(...response.data.results.slice(0, 9));
    },
    onScroll() {
      if ((window.innerHeight + window.scrollY) >= document.body.offsetHeight - 5) {
        this.loadMore();
      }
    },
    loadMore() {
      if (this.currentPage < this.totalPages) {
        this.currentPage += 1;
        this.getCharacters();
      }
    }
  },
  created() {
    this.getCharacters();
    window.addEventListener('scroll', this.onScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll);
  }
}
</script>

<style>
.character-gallery {
  display: grid;
  grid-template-columns: 1fr;
  gap: 20px;
  padding: 20px;
}

  /* Hide scrollbar for Chrome, Safari and Opera */
  ::-webkit-scrollbar {
    display: none;
  }

@media (min-width: 768px) {
  .character-gallery {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .character-gallery {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>

