<template lang="">
    <CardsSelect @filteredCards="getCardsFromFilter" />
    <CardsList :cardsList="cardsList" />
</template>
<script>
import CardsSelect from './CardsSelect.vue'
import CardsList from './CardsList.vue'
import axios from 'axios';

export default {
    name: 'AppMain',
    data() {
        return {
            cardsList: []
        }
    },
    components: {
        CardsSelect,
        CardsList
    },
    methods: {

        getCardsFromFilter(filter){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=' + filter)
                .then( (response) => {
                    // handle success
                    this.cardsList = response.data.data;
                    console.log(this.cardsList);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        }
    },
}
</script>
<style lang="">

</style>