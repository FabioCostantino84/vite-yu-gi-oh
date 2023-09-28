<script>
import { store } from '../store.js'
import Cards from "./Cards.vue"
import AppSelect from './AppSelect.vue'


export default {
    name: 'AppMain',

    components: {
        Cards,
        AppSelect,

    },
    data() {
        return {
            store,
        }
    },
    created() {
        store.fetchData();
    },
    methods: {
        searchArchetype() {
            const url = 'https://db.ygoprodeck.com/api/v7/cardinfo.php' + `?archetype=${store.selectArchetype}`

            console.log(url);
            this.store.base_url = url + '&num=20&offset=0'
            store.fetchData(url)
        }
    },
}
</script>
    
<template>
    <main class="py-4">
        <div class="container">

            <AppSelect @archSearch="searchArchetype()" />

        </div>
        <div class="container p-5 bg-white">
            <div class="container counterCard text-white d-flex align-items-center fw-bold">Founded 20 cards</div>
            <div class="row">
                <Cards v-for="card in store.cards" :card="card" />
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
