<script>
import { store } from '../store.js'

export default {
    name: 'AppSelect',

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
    <select class="form-select mb-4 fs-4" aria-label="">
        <option selected disabled>Select Archetype</option>
        <option value="1">Alien</option>
        <option value="1">Noble Knight</option>
        <option value="2">Tainted Treasure</option>
        <option value="3">Melodious</option>
        <option value="3">Archfiend</option>
    </select>
</template>


<style lang="scss" scoped></style>