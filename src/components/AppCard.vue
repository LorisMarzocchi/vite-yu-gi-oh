<script>
export default {
  name: "AppCard",
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
    <h3>{{ characterData.name }}</h3>
    <p class="type">{{ characterData.archetype }}</p>
  </div>
</template>

<style lang="scss" scoped>
.cards {
  text-align: center;

  background-color: #d48f38;
  margin-inline: 10px;
  margin-bottom: 10px;
}
h3 {
  color: white;
}
p {
  margin: 1rem;
}
img {
  width: 100%;
}
</style>
