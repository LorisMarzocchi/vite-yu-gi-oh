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
  created() {
    // qui fare la richiesta all'api
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => (this.store.cardList = response.data.data));
  },
};
</script>

<template>
  <AppHeader />
  <AppSelector />
  <AppMainList />
</template>

<style lang="scss">
@use "./assets/styles/general.scss" as *;
</style>
