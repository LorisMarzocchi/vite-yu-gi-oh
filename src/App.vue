<script>
import AppHeader from "./components/AppHeader.vue";
import AppSelector from "./components/AppSelector.vue";
import AppMainList from "./components/AppMainList.vue";
import axios from "axios";
import { store } from "./store";
export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppHeader,
    AppSelector,
    AppMainList,
  },
  methods: {
    requestData() {
      axios
        .get(
          `https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0${this.store.value ? '&archetype=' + this.store.value : ''}`
        )
        .then((response) => (this.store.cardList = response.data.data));
    },



  },
  created() {
    this.requestData();
    axios
      .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
      .then((response) => (this.store.optionList = response.data));
  },
};
</script>

<template>
  <AppHeader />
  <AppSelector @pippo="requestData" />
  <AppMainList />
</template>

<style lang="scss">
@use "./assets/styles/general.scss" as *;
</style>