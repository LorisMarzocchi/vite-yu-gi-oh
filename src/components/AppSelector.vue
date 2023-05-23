<script>
import { type } from "../store";

export default {
  data() {
    return {
      type,
    };
  },
};
</script>

<template>
  <div>
    <select v-model="type.value" class="form-select">
      <option
        v-for="option in type"
        :key="option.archetype_name"
        :value="option"
      >
        {{ option }}
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
