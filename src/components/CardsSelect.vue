<template lang="">
    <div>
        <label for="cards-select"></label>
        <select name="cards-select" id="cards-select" v-model="selectedFilter">
            <option  value=""></option>
        </select>
    </div>
</template>
<script>
import axios from 'axios';

export default {
    name: 'CardsSelect',
    data() {
        return {
            selectedFilter : ''
        }
    },
}
</script>
<style lang="scss">

</style>