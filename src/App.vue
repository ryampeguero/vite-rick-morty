<script>
import AppHeader from "./components/AppHeader.vue";
import AppStatus from "./components/AppStatus.vue"
import AppCardList from "./components/AppCardList.vue";
import AppBuffer from "./components/AppBuffer.vue";
import axios from "axios";

import { store } from "./store.js";

export default {
  components: {
    AppHeader,
    AppStatus,
    AppCardList,
    AppBuffer
  },

  data() {
    return {
      charArray: [],
      loadingBool: false,
      store, //Global Var
    }
  },

  created() {
    this.callApi();
  },

  methods: {
    loadingBuffer() {
      // setTimeout(() => {this.loadingBool = !this.loadingBool;
      // }, 1000); Questo era un test

      this.loadingBool = true;

      console.log("Bool:", this.loadingBool);
    },

    callApi() {
      this.loadingBool = false;

      const paramsObj = {
        status: " ",
      };

      console.log("ciao", paramsObj.status);

      if (store.selectedStatus !== "All") {
        paramsObj.status = store.selectedStatus;
      }

      console.log("ciao", paramsObj.status);

      axios.get("https://rickandmortyapi.com/api/character", { params: paramsObj }).then((resp) => {
        console.log(resp.data.results);
        store.cardContainer = resp.data.results;
        this.loadingBuffer();
      });
    }
  }
}
</script>

<template>

  <AppHeader />

  <AppStatus @filter="callApi" />

  <AppCardList v-if="loadingBool"/>

  <AppBuffer v-else />

</template>

<style></style>