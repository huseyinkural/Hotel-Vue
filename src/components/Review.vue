<template>
  <div class="row justify-content-center">
    
    
  

   
      
          <div class="circle">              
            <p>{{review.point}}</p>         
          </div>
          <div class="col-4">
            <p>{{review.comment}}</p>  
          </div>
           <div class="col-1">
            <p>{{review.email}}</p>  
          </div>
         


      
  </div>
</template>

<script>
export default {

  props:['review']



}
</script>

<style scoped>
.circle{
  
  border-style: solid;
  border-color: coral;
  width: 50px;
  height: 50px;
  line-height: 40px;
  border-radius: 50%;
  -moz-border-radius: 50%;
  -webkit-border-radius: 50%;
  text-align: center;   
  text-transform: uppercase;
   background-color: darkgray; 
  
}


.row{

    margin-top: 10px;
    
  /* To adjust the height as well */ 
 
  background-color: brown;
  
  
}

.col-4{
 
   border-style: solid;
  border-color: coral;

}

</style>