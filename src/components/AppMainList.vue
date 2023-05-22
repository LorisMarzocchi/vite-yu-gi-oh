<script>
import AppCard from "./AppCard.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  component: {
    AppCard,
  },
};
</script>

<template>
  <div class="containerCard">
    <div class="countCard">Found 20 cards</div>
    <AppCard
      v-for="card in store.cardList"
      :key="card.id"
      :characterData="card"
    />
  </div>
</template>

<style lang="scss" scoped>
.containerCard {
  height: 100vh;
  margin: auto;
  width: 80%;
  background-color: white;
}
.countCard {
  height: 3rem;
  color: white;
  background-color: black;
}
</style>
