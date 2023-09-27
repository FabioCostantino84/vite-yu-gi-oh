<script>
import { store } from '../store.js'
import AppSelect from './AppSelect.vue'
import Cards from "./Cards.vue";


export default {
    name: 'AppMain',

    components: {
        AppSelect,
        Cards,
    },
    data() {
        return {
            store
        }
    },
    created() {
        store.fetchData();
    }
}
</script>
    
<template>
    <main class="py-4">

        <div class="container">

            <AppSelect />

            <!-- <select class="form-select mb-4 fs-4" aria-label="">
                <option selected disabled>Select Archetype</option>
                <option value="1">Alien</option>
                <option value="1">Noble Knight</option>
                <option value="2">Tainted Treasure</option>
                <option value="3">Melodious</option>
                <option value="3">Archfiend</option>
            </select> -->

        </div>


        <div class="container p-5 bg-white">
            <div class="container counterCard text-white d-flex align-items-center fw-bold">Founded 50 cards</div>
            <div class="row">
                <Cards v-for="card in store.cards" :card="card" />
               <!--  <div class="my_col" v-for="card in store.cards">
                    <div class="card">
                        <img class="w-100" :src='card.card_images[0].image_url' alt="">
                        <div style="height: 150px;" class="card-body  mb-3">
                            <h5 class="card-title text-uppercase text-align-center text-white">{{ card.name }}</h5>
                            <p class="card-text">{{ card.archetype }}</p>
                        </div>
                    </div>
                </div> -->
            </div>
        </div>
    </main>
</template>


<style lang="scss" scoped>
@use '../assets/scss/partials/variable.scss' as *;

main {
    background-color: $yugioh__bg;
}



.counterCard {
    background-color: black;
    height: 50px;
    padding: 30px 15px;
}

</style>
