<template>
  <select
    name="genre-select"
    id=""
    v-model="selectedOption"
    @change="emitChange"
  >
    <option value="">{{ placeholder || "Seleziona un genere" }}</option>
    <option
      v-for="option in options"
      :key="option.value || option"
      :value="option.value || option"
    >
      {{ option.label || option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "BaseSelect",
  data() {
    return {
      selectedOption: "",
    };
  },

  props: {
    options: Array,
    placeholder: String,
  },

  methods: {
    emitChange() {
      this.$emit("option-change", this.selectedOption);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>