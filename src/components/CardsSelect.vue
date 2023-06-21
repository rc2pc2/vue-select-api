<template lang="">
    <div>
        <label for="cards-select"></label>
        <select name="cards-select" id="cards-select" v-model="selectedFilter"
            @change="$emit('filteredCards', selectedFilter)">
            <option v-for="cardArchetype in cardsArchetypes" :value="cardArchetype.archetype_name" >
                {{ cardArchetype.archetype_name }}
            </option>
        </select>
    </div>
</template>
<script>
import axios from 'axios';

export default {
    name: 'CardsSelect',
    data() {
        return {
            selectedFilter : '',
            cardsArchetypes : [],
        }
    },

    methods: {
        getArchetypes(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
                .then( (response) => {
                    // handle success
                    this.cardsArchetypes = response.data.slice(0, 30);
                    console.log(this.cardsArchetypes);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        },
    },

    created(){
        this.getArchetypes();
    }
}
</script>
<style lang="scss">

</style>