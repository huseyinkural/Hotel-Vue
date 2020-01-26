<template>

     <div class="row">
        <app-card v-for="card in cards"  :key="card" :card="card">{{ card }}</app-card>
    </div>
  
</template>

<script>

import Card from './Card.vue'

export default {

    props: ['cards'],

    components: {
        appCard: Card
    }

}
</script>

<style>

</style>