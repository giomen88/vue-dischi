<template>
  <header>
    <div>
      <img src="../assets/img/logo.png" alt="" class="logo img-fluid" />
    </div>

    <BaseSelect
      :options="genresList"
      placeholder="Seleziona un genere"
      @option-change="emitGenreChange"
    />
  </header>
</template>

<script>
import BaseSelect from "./BaseSelect.vue";

export default {
  name: "AppHeader",
  components: { BaseSelect },
  props: {
    genresList: Array,
  },
  data() {
    return {};
  },
  methods: {
    emitGenreChange(genre) {
      this.$emit("genre-change", genre);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/vars";

header {
  background-color: $bg-secondary;
  height: 70px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;

  img {
    width: 50px;
  }
}
</style>