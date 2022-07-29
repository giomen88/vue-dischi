<template>
  <main>
    <div
      class="
        container
        py-5
        d-flex
        justify-content-center
        align-items-center
        flex-wrap
      "
    >
      <DiscCard v-for="disc in filteredDiscs" :key="disc.title" :disc="disc" />
    </div>
  </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";

export default {
  name: "AppMain",
  components: {
    DiscCard,
  },
  props: {
    filteredDiscs: Array,
  },
};
</script>

<style lang="scss" scoped>
</style>