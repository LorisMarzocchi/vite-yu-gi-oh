<script>
import AppCard from "./AppCard.vue";
import { store } from "../store";
export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppCard,
  },
};
</script>

<template>
  <div class="containerCard">
    <div class="countCard">Found 20 cards</div>
    <div class="container">
      <AppCard v-for="(cards, index) in store.cardList" :key="index" class="card-character" :characterData="cards" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card-character {
  width: calc((100% / 5) - 20px);
}

.container {
  display: flex;
  flex-wrap: wrap;
}

.containerCard {
  padding: 20px;
  height: 100%;
  margin: auto;
  width: 80%;
  background-color: white;
}

.countCard {
  text-align: center;
  padding: 1rem;
  margin-inline: 10px;
  height: 3rem;
  color: white;
  background-color: black;
}
</style>