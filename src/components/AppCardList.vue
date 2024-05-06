<script>
import CharacterCard from "./CharacterCard.vue";
export default {
    components: {
        CharacterCard,
    },

    props: {
        charArray: [],
    },

    data(){
        
    },

    created(){
        // console.warn("ciao", this.charArray);
    }
}
</script>

<template>
    <div class="container justify-content-center align-items-center text-center">
        <div class="row">
            <div v-for="char in charArray" class="col-3 border p-3">
                <CharacterCard :char="char"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>