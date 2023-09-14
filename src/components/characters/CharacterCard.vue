<script>
export default {
  props: {
    image: String,
    name: String,
    archetype: String,
  },
};
</script>

<template>
  <div class="col-3 card">
    <img :src="image" alt="img" />
    <div class="card-body text-center">
      <h5 class="card-title">{{ name }}</h5>
      <p class="card-text">
        {{ archetype }}
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  border: none;
  margin: 0;
  padding: 0.5rem;
  .card-body {
    background-color: #d48f38;
  }
}
</style>
