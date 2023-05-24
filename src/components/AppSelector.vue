<script>
import { store } from "../store";
export default {
  data() {
    return {
      store,
    };
  },
  methods: {
    onChange() {
      this.$emit("pippo");
    },
  },
};
</script>

<template>
  <div>
    <select @change="onChange" v-model="store.value" class="form-select">
      <option v-for="option in store.optionList" :key="option.archetype_name" :value="option.archetype_name">
        {{ option.archetype_name }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
div {
  margin-inline: 100px;
  margin-top: 50px;
  margin-bottom: 20px;
}
</style>