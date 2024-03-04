<template>
  <div class="container">
          <span v-if="included">
                    <CheckCircle2
                              fill="#1a98ff"
                              stroke="#0f171e"
                              :width="width"
                              :height="height"
                    />
                    <p>Included with {{ provider }}</p>
          </span>
          <span v-else>
                    <ShoppingBag
                    fill="yellow"
                    :height="heigth"
                    :width="width"
                    />
                    <p>Free trial of {{ provider }}, rent, or buy</p>
          </span>
  </div>
</template>

<script>

import { ShoppingBag } from 'lucide-vue-next';
 import { CheckCircle2 } from 'lucide-vue-next'

export default {
          data(){
                    return{
                              height:20,
                              width:20
                    }
          },
          props:{
                    provider:String,
                    included:Boolean
          },
          components:{
                    ShoppingBag,
                    CheckCircle2
          }
}
</script>

<style>
.container p{
          color: #fff;
}
          
          .container span{
                    display: flex;
                    flex-direction: row;
                    justify-content: center;
                    align-items: flex-end;

                    margin:0 0.6rem;
                    background: transparent;
          }
          .container span p{
                    
                    font-size: 13pt;
                    padding-inline-start: 8px;
          }
</style>