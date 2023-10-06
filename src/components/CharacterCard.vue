<template>
  <div class="character-card">
    <img :src="character.image" :alt="character.name" class="character-card__image">
    <h2 class="character-card__name">{{ character.name }}</h2>
    <p class="character-card__status">Status: {{ character.status }}</p>
    <p class="character-card__created">Created: {{ character.created }}</p>
    <p class="character-card__location">Location: {{ character.location.name }}</p>
  </div>
</template>

<script>
export default {
  props: {
    character: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped lang="scss">
  .character-card {
    border: 1px solid #ccc;
    padding: 15px;
    border-radius: 5px;
    transition: transform 0.3s;

    &:hover {
      transform: scale(1.02);
    }

    &__image {
      width: 100%;
      border-radius: 5px;
      margin-bottom: 15px;
    }

    &__name {
      font-size: 1.2em;
      margin-bottom: 10px;
    }

    &__status,
    &__created,
    &__location {
      font-size: 0.9em;
      margin-bottom: 8px;
    }
  }

</style>
