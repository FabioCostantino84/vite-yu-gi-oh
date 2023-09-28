<script>
import {store} from '../store.js'

export default {
    name: 'AppSelect',
    emits: ['archSearch'],
    data () {
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
    <div class="py-3">
        <select class="form-select w-25" aria-label="Default select example" @change="$emit('archSearch')" v-model="store.selectArchetype">
            <option disabled value="">Select Archetype</option>
            <option value="Alien">Alien</option>
            <option value="Noble Knight">Noble Knight</option>
            <option value="Melodious">Melodious</option>
            <option value="Archfiend">Archfiend</option>
        </select>
    </div>
</template>

<style lang="scss" scoped></style>
