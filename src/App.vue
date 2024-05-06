<script>
import AppHeader from "./components/AppHeader.vue";
import AppCardList from "./components/AppCardList.vue";
import axios from "axios";

export default {
  components: {
    AppHeader,
    AppCardList
  },

  data() {
    return {
      charArray: [],
    }
  },

  created() {
    axios.get("https://rickandmortyapi.com/api/character", {
      params: {},
    }).then((resp) => {
      // console.log(resp.data.results);
      this.charArray = resp.data.results;
    });
  }
}
</script>

<template>

  <AppHeader />

  <AppCardList :charArray="charArray"/>
</template>

<style></style>