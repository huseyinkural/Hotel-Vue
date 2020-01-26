<template>
    <div class="container">

        <app-card-grid :cards="cards"></app-card-grid>
        <app-card-detail></app-card-detail>
    
    </div>
</template>

<script>

    import CardGrid from './components/CardGrid.vue'
    import CardDetail from './components/CardDetail.vue'
    import {hotels} from './data/hotels.js'
  

    export default {
         data: function () {
            return {
                cards: null,
                          
            }
        },

        components:{
            appCardGrid: CardGrid,
            appCardDetail: CardDetail
        },
        created(){
            this.cards = hotels;           
        }
    }
</script>

<style>
    .container{
        margin-top: 20px;
    }
</style>
