<script>
import { store } from '../store.js'

export default {
    name: 'AppMain',
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

            <select class="form-select mb-4 fs-4" aria-label="">
                <option selected>Alien</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>

        </div>


        <div class="container p-5 bg-white">
            <div class="container counterCard text-white d-flex align-items-center">Founded 50</div>
            <div class="row">
                <div class="my_col" v-for="card in store.cards">
                    <div class="card">
                        <img class="w-100" :src='card.card_images[0].image_url' alt="">
                        <div style="height: 150px;" class="card-body  mb-3">
                            <h5 class="card-title text-uppercase text-align-center text-white">{{ card.name }}</h5>
                            <p class="card-text">{{ card.archetype }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>


<style lang="scss" scoped>
@use '../assets/scss/partials/variable.scss' as *;
main {
    background-color: $yugioh__bg;
}

select{
    width: 15%;
}

.counterCard {
    background-color: black;
    height: 50px;
}

.my_col {
    width: calc(100% / 10 * 2);
}

.card{
    border: none;
}

.card-body{
    background-color: $yugioh__bg;
    text-align: center;

}
</style>