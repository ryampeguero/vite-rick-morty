<script>
import CharacterCard from "./CharacterCard.vue";
import {store} from "../store.js"
export default {
    components: {
        CharacterCard,
    },

    data(){
        return {
            store,
        }
    },

    created(){
        // console.warn("ciao", this.charArray);
    }
}
</script>

<template>
    <div class="container justify-content-center align-items-center text-center">
        <div class="row">
            <div v-for="char in store.cardContainer" class="col-3 p-3">
                <CharacterCard :char="char"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>