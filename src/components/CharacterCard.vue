<script>

export default {
    props: {
        char: Object,
    },

    created() {
        console.log("Obge", this.char);
    }
}
</script>

<template>
    <div class="">
        <img :src="this.char.image" class="card-img-top img-thumbnail rounded-circle" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ this.char.name }}</h5>
            <div class="card-text">{{ this.char.status }}</div>
            <div class="card-text">{{ this.char.species }}</div>
            
        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>