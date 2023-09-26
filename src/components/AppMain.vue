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
        <div class="container bg-white">
            <div class="container counterCard text-white">Founded 50</div>
            <div class="row p-2">
                <div class="my_col p-2" v-for="card in store.cards">
                    <div class="card">
                        <img class="w-100" :src='card.card_images[0].image_url' alt="">
                      <div style="height: 120px;" class="card-body ">
                        <h5 class="card-title text-uppercase text-align-center">{{ card.name }}</h5>
                        <p class="card-text">{{ card.archetype }}</p>
                      </div>
                    </div>
                </div>
            </div>
        </div>
    </main>


</template>


<style lang="scss" scoped>

main{
    background-color: orange;
}

.counterCard{
    background-color: black;
    height: 50px;
}
.my_col{
    width: calc(100% / 10 * 2);
}

</style>