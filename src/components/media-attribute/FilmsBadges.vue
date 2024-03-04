<template>
     <div class="container">
          <span>
               <p>X-RAY</p>
          </span>
          <span>
               <p>HDR</p>
          </span>
          <span>
               <p>UDR</p>
          </span>
          <span>
                    <img class="parental" src="../../assets/parentalRatingIcons/L.png" alt="parentalRatingAlt">
          </span>
          <span>
               <Captions/>
          </span>
          <span>
                    <img src="../../assets/icons/AudioDesciption.png" alt="">
          </span>
     </div>
</template>

<script>

import {Captions} from 'lucide-vue-next';

export default {
     components:{
          Captions
     },
     props:{
          parentalRatingImage:String,
          parentalRatingAlt:String
     }
}
</script>

<style scoped>
          .container{
                    display: flex;
          }
          .parental{
                    height: 85%;
          }
          span{
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    color: white;
                    font-weight: bolder;

                    background:hsla(0, 0%, 100%, .2);
                    
                    margin: 2px;
                    height: 30px;
                    width: fit-content;
                    padding: 0.5% 1%;

                    border-radius: 4px;
          }
</style>