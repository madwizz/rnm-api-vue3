<script>
import CharacterGallery from './components/CharacterGallery.vue';
import Header from './components/Header.vue';

export default {
  components: {
    Header,
    CharacterGallery,
  }
}
</script>

<template>
  <div class="page">
    <Header />
    <CharacterGallery />
  </div>
</template>

<style scoped>
</style>
