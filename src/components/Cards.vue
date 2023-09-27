<script>
import { store } from '../store.js'

export default {
    name: 'Cards',

    props: ['card'],

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
    <div class="my_col">
        <div class="card">
            <img class="w-100" :src='card.card_images[0].image_url' alt="">
            <div style="height: 150px;" class="card-body  mb-3">
                <h5 class="card-title text-uppercase text-align-center text-white">{{ card.name }}</h5>
                <p class="card-text">{{ card.archetype }}</p>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
@use '../assets/scss/partials/variable.scss' as *;


.counterCard {
    background-color: black;
    height: 50px;
    padding: 30px 15px;
}

.my_col {
    width: calc(100% / 10 * 2);
}

.card {
    border: none;
}

.card-body {
    background-color: $yugioh__bg;
    text-align: center;

}

</style>