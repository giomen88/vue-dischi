<template>
  <div
    class="disc-card d-flex flex-column justify-content-between p-4 text-center"
  >
    <img :src="disc.poster" :alt="disc.title" class="img-fluid mb-3" />
    <h5 class="text-white">{{ uppercaseTitle }}</h5>
    <p class="text-secondary fs-4">{{ disc.author }}</p>
    <p class="text-secondary fs-5">{{ disc.year }}</p>
  </div>
</template>

<script>
export default {
  name: "DiscCard",
  props: {
    disc: Object,
  },
  computed: {
    uppercaseTitle() {
      return this.disc.title.toUpperCase();
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/vars";
.disc-card {
  margin: 10px;
  flex-basis: calc(20% - 20px);
  min-height: 450px;
  background-color: $bg-secondary;
}
</style>