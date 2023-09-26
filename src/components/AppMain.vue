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
            <div class="row p-2">
                <div class="col-3 p-1" v-for="card in store.cards">
                    <div class="card" style="width: 18rem;">
                        <img class="w-100" :src='card.card_images[0].image_url' alt="">
                      <div class="card-body">
                        <h5 class="card-title">Card title</h5>
                        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                        <a href="#" class="btn btn-primary">Go somewhere</a>
                      </div>
                    </div>
                    
                </div>
            </div>
        </div>
    </main>


</template>


<style lang="scss" scoped>

</style>