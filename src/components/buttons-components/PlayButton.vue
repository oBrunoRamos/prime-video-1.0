<template>
  <div class="container">
          <button @mouseenter="PlayGrow"  @click="PlayDown">
                    <Play 
                               fill="#000"
                    
                              heigth="20"
                              width="20"
                    />
          </button>
          <p>Play</p>
          <div  v-if="series" class="container serie">
                    <p> {{ season }} </p>
                    <p>{{ episode }}</p>
          </div>
  </div>
</template>

<script>
import  { Play } from 'lucide-vue-next';

export default {
          data(){
                    return{
                              series:true,
                              season: 'S1',
                              episode: 'E1'
                    }
          },
          components:{
                    Play,
          },
          props:{           
                    // series:Boolean,
                    // season:String,
                    // episode:String
          },
          methods:{
                    PlayGrow(event){
                              const play = event.currentTarget.firstElementChild;
                              console.log(play);
                              
                    },
                    PlayDown(){

                    }
          }
}
</script >
<style scoped>
          .container{
                   display: flex;

                   flex-direction: row;
                   align-items: center;

                   width: 100%;
                   height: 20%;

                   background: rebeccapurple
          }
          .container p{
                    font-weight: bold;
                    font-size: 80%;

                    padding-left: .5rem;
          }
          .container button{
                    display: flex;
                    align-items: center;
                    justify-content: center;

                    height: 3.5rem;
                    width: 3.5rem;
                    
                    border: none;
                    border-radius: 100%;

                    background: #fff;
          }
          .serie{
                    padding-left: .5rem;
          }
          .serie p{
                    padding: 0.2rem;
          }
</style>