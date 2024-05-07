<script>
import { store } from "../store.js";

export default {
    data(){
        return{
            store,
            status: ["All", "Alive", "Dead", "Unknown"],
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <select @change="$emit('filter')" v-model="store.selectedStatus">
                    <option v-for="option in status" :value="option">{{ option }}</option>
                </select>
            </div>
            <div class="col"></div>
            <div class="col">
                <div class="d-flex justify-content-end">
                    <span>Mostra {{ store.cardContainer.length }} risultati</span>
                </div>
            </div>
        </div>
    </div>
</template>

<style></style>