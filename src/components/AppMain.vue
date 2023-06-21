<template lang="">
    <CardsSelect />
    <CardsList />
</template>
<script>
import CardsSelect from './CardsSelect.vue'
import CardsList from './CardsList.vue'


export default {
    name: 'AppMain',
    components: {
        CardsSelect,
        CardsList
    }
}
</script>
<style lang="">

</style>