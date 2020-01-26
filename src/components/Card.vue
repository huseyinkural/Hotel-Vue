<template>
  <div class="col-sm-6 col-md-3 col-lg-4">
       <div class="card" @click="detail(card.id)">
        <img class="card-img-top" :src=card.img alt="Card image cap">
        <div class="card-body text-center">
            <a href="www.google.com" class="card-title">{{card.name}}</a>
            <p class="card-text">Price: {{card.price}}</p>
            <a href="#" class="btn btn-success" @click="detail(card.id)">Detail</a>
        </div>
</div>
    </div>
</template>

<script>
import {eventBus} from '../main'
export default {

    props:['card'],

    methods:{
        detail(index){
            eventBus.$emit('detail',index);
           
        }
    }


}
</script>

<style>
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: 5px; /* 5px rounded corners */
}

.card-img-top{
    height: 200px;
    width: 100%;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}



</style>