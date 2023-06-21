<template lang="">
    <article class="single-card" v-for="card in cardsList">
        <h2>
            {{ card.name }}
        </h2>
    </article>
</template>
<script>

export default {
    name: 'CardsList',
    props : {
        cardsList : Array
    }
}
</script>
<style lang="">

</style>