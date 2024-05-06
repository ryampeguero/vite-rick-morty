<script>
import AppHeader from "./components/AppHeader.vue";
import AppCardList from "./components/AppCardList.vue";
import AppBuffer from "./components/AppBuffer.vue";
import axios from "axios";

export default {
  components: {
    AppHeader,
    AppCardList,
    AppBuffer
  },

  data() {
    return {
      charArray: [],
      loadingBool: false,
    }
  },

  created() {
    axios.get("https://rickandmortyapi.com/api/character", {
      params: {},
    }).then((resp) => {
      // console.log(resp.data.results);
      this.charArray = resp.data.results;
      this.loadingBuffer();
    });
  },

  methods: {
    loadingBuffer(){
      // setTimeout(() => {this.loadingBool = !this.loadingBool;
      // }, 1000); Questo era un test
      
      this.loadingBool = !this.loadingBool;

      console.log("Bool:", this.loadingBool);
    }
  }
}
</script>

<template>

  <AppHeader />

  <AppCardList v-if="loadingBool" :charArray="charArray"/>

  <AppBuffer v-else/>

</template>

<style></style>