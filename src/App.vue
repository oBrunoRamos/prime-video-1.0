<template>
  <div id="app">
          <NavBar/>
          <MediaView/>
  </div>
</template>

<script>

import NavBar from './components/global-components/NavBar.vue';
import MediaView from './views/MediaView.vue';

export default {
     data(){
          return{
               parentalImage:'./assets/parentalRatingIcons/L.png',

          }
     },
     components:{
          NavBar,
          MediaView
     }
}
</script>

<style>
     #app{
          height: 100vh;
          width: 100vw;

          background: #00060a;

          font-family: sans-serif;
     }
     span{

          height: fit-content;
          width: fit-content;

          background: #665;
     }
</style>