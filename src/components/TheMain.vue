<template>
  <main>
    <div
      class="
        container
        py-5
        d-flex
        justify-content-between
        align-items-center
        flex-wrap
      "
    >
      <DiscCard v-for="disc in discs" :key="disc.title" :disc="disc" />
    </div>
  </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";
export default {
  name: "TheMain",
  components: {
    DiscCard,
  },
  props: {
    discs: Array,
  },
};
</script>

<style lang="scss" scoped>
</style>