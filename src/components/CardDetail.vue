<template>
<div v-if="isDisabled">
  
 
  
     <div class="row justify-content-center">
       <div class="col-6">
         <p>detail: {{cardId}}</p> 
         <div class="slide">
      
      <!-- swiper -->

      <swiper :options="swiperOption">
        <swiper-slide><img src="https://q-cf.bstatic.com/images/hotel/max1024x768/130/130819460.jpg" alt=""></swiper-slide>
        <swiper-slide><img src="https://pix10.agoda.net/hotelImages/4862270/0/1c6b57e935f7f6aa015d9478f8c5f252.jpg?s=1024x768" alt=""></swiper-slide>
        <swiper-slide>Slide 3</swiper-slide>
        <swiper-slide>Slide 4</swiper-slide>
        <swiper-slide>Slide 5</swiper-slide>
        <swiper-slide>Slide 6</swiper-slide>
        <swiper-slide>Slide 7</swiper-slide>
        <swiper-slide>Slide 8</swiper-slide>
        <swiper-slide>Slide 9</swiper-slide>
        <swiper-slide>Slide 10</swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
        <div class="swiper-button-prev" slot="button-prev"></div>
        <div class="swiper-button-next" slot="button-next"></div>
      </swiper>
    </div>
       </div>
       

    </div>

    <app-review v-for="rev in revs" :review="rev"></app-review>


  

    

</div>

  
</template>

<script>
import {eventBus} from "../main";
// require styles
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper';
import Review from './Review.vue';
import {reviews} from '../data/review.js'




export default {
     data: function () {
            return {

                cardId:'',
                revs:null,               
                isDisabled: false,              
                swiperOption: {
                  slidesPerView: 1,
                  spaceBetween: 30,
                  loop: true,
                  pagination: {
                    el: '.swiper-pagination',
                    clickable: true
                  },
                  navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev'
                  }
                }               
                 
               
            }
      },

    created() {

      
    eventBus.$on('detail', (id) => {
        this.cardId = id;
        this.isDisabled = true;
        this.revs = reviews.filter(function(rev){
          return rev.hotelId === id;

        });

        console.log('revs: '+ this.revs);
       
        
    });
   
    },
  
    
    methods: {
    
    },
    components: {
      swiper,
      swiperSlide,
      appReview: Review      
    },

    

}
</script>

<style>
img{
  width: 100%;
  
}

.slide{
  
 
}
.row{
 
}
</style>