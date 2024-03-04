<template>
<div>
     <div>
          <video v-if="trailer" :src="trailerUrl"></video>
          <img v-else :src="tumbUrl" :alt="tumbAlt">      
     </div>
     <div v-if="prime">
          <h4>Included with prime</h4>
     </div>
     <div>
          <button name="playerButton">Play</button>
          <label for="playerButton">Play {{ season }} {{ episode }}</label>
          <div>
               <button>Add</button>
               <button>Remove</button>
          </div>
     </div>
     <div>
          <div>{{ title }}</div>
          <div>
               <p>{{ releaseYear }}</p>
               <p v-if="movieTime">{{ movieTime }}</p>
               <p>{{ parentalRating }}</p>
          </div>
          <div>
               {{ award }}
          </div>
          <div>{{ description }}</div>
     </div>
</div>
</template>

<script>
export default {
     data(){
          return{
               trailer: true,
               trailerUrl: '',

               tumbUrl: '',
               tumbAlt: '',

               prime: '',
               season: 'Season 1',
               episode: '',

               title: '',
               releaseYear: '',
               movieTime: '',
               parentalRating: '',
               award:'',
               description: ''
          }
     },
     methods:{
          shortnetDescription(){
               let desc = this.description
               if(desc.length>80){
                    this.description = desc.slice(0,78)+'...';
               }
          },
          Frase(){
               const frase = "Optimus Prime and the Autobots take on their biggest challenge yet. When a new".length
               console.log(frase);
               return null
          },
     
          // Função para abreviar a Season
          shortenedSeason(){
               return this.season[0]+this.season.slice(-1)
          }
     },
     
     created(){
          this.shortnetDescription();
          this.shortenedSeason();
          this.Frase()
     }
  
}
</script>

<style>

</style>