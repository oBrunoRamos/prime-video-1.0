<template>
          <div class="container">
                              <button v-if="trailerActive" class="button-style">
                                        <Film  
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />
                              </button>
                              <button v-if="plusActive" class="button-style">
                                        <Plus
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />
                              </button>
                              <button  v-if="upActive"  class="button-style">
                                        <ThumbsUp
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />          
                              </button>
                              <button v-if="downActive" class="button-style">
                                        <ThumbsDown
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />
                              </button>
                              <button v-if="downloadActive" class="button-style">
                                        <Download
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />        
                              </button>
                              <button v-if="partyActive" class="button-style">
                                        <PartyPopper
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />                          
                              </button>   
                              <button v-if="shareActive" class="button-style">                                        
                                        <Share2
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />
                              </button>                                             
                              <button v-if="moreActive" class="button-style">
                                        <MoreVertical
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />        
                              </button>
                              <button v-if="xActive" class="button-style">
                                        <XCircle
                                                  :fill="color"
                                                  :stroke="stroke"
                                                  :heigth="heigth"
                                                  :width="width"
                                        />
                              </button> 
          </div>
</template>

<script>

import {Plus} from 'lucide-vue-next';
import {ThumbsUp} from 'lucide-vue-next';
import {ThumbsDown} from 'lucide-vue-next';
import {PartyPopper} from 'lucide-vue-next';
import {XCircle} from 'lucide-vue-next';
import {Share2} from 'lucide-vue-next';
import {MoreVertical} from 'lucide-vue-next';
import {Film} from 'lucide-vue-next';
import {Download} from 'lucide-vue-next';

export default {
          data(){
                    return{
                              // Icon style
                             color:"hsla(0, 0%, 100%, 0)",
                              stroke:'#fff',

                             heigth:"40",
                             width:"40"



                    }
          },
          components:{
                    Plus,
                    ThumbsUp,
                    ThumbsDown,
                    PartyPopper,
                    XCircle,
                    Share2,
                    MoreVertical,
                    Download,
                    Film
          },
          props:{
                    plusActive:Boolean,
                    upActive:Boolean,
                    downActive:Boolean,
                    partyActive:Boolean,
                    xActive:Boolean,
                    shareActive:Boolean,
                    moreActive:Boolean,
                    trailerActive:Boolean,
                    downloadActive:Boolean

          },
          methods:{
             
          }
}
</script>

<style scoped>
          .container{
                    display: flex;
                    flex-direction: row;
          }
          .button-style{
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    width: 3rem;
                   height: 3rem;
                   margin: 0 0.2rem;

                   background:hsla(0, 0%, 100%, .2);
                   
                   border: none;
                    border-radius: 100%;

          }
</style>
