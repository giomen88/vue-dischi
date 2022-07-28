<template>
  <div>
    <TheHeader />

    <TheMain :discs="discs" />
  </div>
</template>

<script>
import axios from "axios";
import TheHeader from "./components/TheHeader.vue";
import TheMain from "./components/TheMain.vue";

export default {
  name: "App",
  components: {
    TheHeader,
    TheMain,
  },
  data() {
    return {
      discs: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.discs = res.data.response;
        console.log(this.discs);
      });
  },
};
</script>

<style lang="scss">
@import "./assets/sass/style.scss";
</style>
