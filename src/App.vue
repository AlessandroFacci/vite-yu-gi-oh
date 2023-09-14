<script>
import axios from "axios";
import { store } from "../src/data/store";

import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {
      store,
    };
  },
  methods: {
    fetchCharacters(endpoint) {
      axios.get(endpoint).then((res) => {
        store.characters = res.data.data;
      });
    },
  },

  created() {
    this.fetchCharacters(store.apiUri);
  },

  components: { AppHeader, AppMain },
};
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain></AppMain>
</template>

<style lang="scss">
@use "./assets/scss/style.scss";
</style>
