<script>
export default {
  props: {
    characterData: Object,
  },
};
</script>

<template>
  <div class="cards">
    <img
      :src="characterData.card_images[0].image_url"
      :alt="characterData.name"
    />
    <h2>{{ characterData.name }}</h2>
  </div>
</template>

<style lang="scss" scoped>
.cards {
  height: 200px;
  width: 100px;
  border: 1px solid black;
}
</style>
