<script>
import { store } from '../store.js'

export default {
    name: 'AppSelect',
    emits: ['archetypeSearch'],


    data() {
        return {
            store,
        }
    },
    created() {
        store.fetchData();
    },
}

</script>
<template>
    <select class="form-select mb-4 fs-4" @change="$emit('archetypeSearch')" v-model="store.archetypeSelect">
        <option selected disabled>Select Archetype</option>
        <option value="1">Alien</option>
        <option value="1">Noble Knight</option>
        <option value="2">Tainted Treasure</option>
        <option value="3">Melodious</option>
        <option value="3">Archfiend</option>
    </select>
</template>


<style lang="scss" scoped>

select {
    width: 20%;
}


</style>