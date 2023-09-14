<script>
import CharacterCard from "./CharacterCard.vue";
import { store } from "../../data/store";

export default {
  data() {
    return {
      store,
    };
  },

  components: { CharacterCard },
};
</script>

<template>
  <div class="container">
    <select class="form-select mt-4" aria-label="Default select example">
      <option selected>Select archetype</option>
      <option value="1">One</option>
      <option value="2">Two</option>
      <option value="3">Three</option>
    </select>
  </div>
  <div class="container mt-4">
    <div class="row row-cols-lg-5">
      <!-- <div
        class="col-3 card"
        v-for="character in characters"
        :key="character.id"
      >
        <img
          v-for="img in character.card_images"
          :src="img.image_url_small"
          alt="img"
        />
        <div class="card-body text-center">
          <h5 class="card-title">{{ character.name }}</h5>
          <p class="card-text">
            {{ character.archetype }}
          </p>
        </div>
      </div> -->
      <CharacterCard
        v-for="character in store.characters"
        :key="character.id"
        :image="character.image_url_small"
        :name="character.name"
        :archetype="character.archetype"
      >
      </CharacterCard>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  width: 1180px;
  .form-select {
    width: 15rem;
  }
}
.container:last-child {
  width: 1180px;
  padding: 3rem;
  background-color: white;
}
</style>
