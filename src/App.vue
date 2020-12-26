<template>
  <div id="app">
    <app-navbar></app-navbar>
    <app-home></app-home>  
    <app-experience></app-experience> 
  </div>
</template>

<script>
import Navbar from './components/DesNavbar.vue';
import Home from './components/Home.vue';
import Experience from './components/Experience.vue';

export default {
  components:{
    appNavbar:Navbar,
    appHome:Home,
    appExperience:Experience
  },
  data(){
    return {
      oldScroll:0,
      newScroll:0
    }
  },
  computed:{
    scrollPos(){
      return window.pageYOffset
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600&display=swap');
*{
  margin:0;
  padding:0;
  box-sizing: border-box;
}
#app{
  position: relative;
  width: 100%;
  min-height: 100vh; 
  
  /* background-image: linear-gradient(147deg, #923cb5 0%, #211727 74%); */
  font-family: 'Montserrat', sans-serif;
  overflow-x: hidden;
}
body::-webkit-scrollbar {
    background-color: #fff;
    width: 16px;
}

/* background of the scrollbar except button or resizer */
body::-webkit-scrollbar-track {
    background-color: #fff;
}

/* scrollbar itself */
body::-webkit-scrollbar-thumb {
    background-color: #babac0;
    border-radius: 16px;
    border: 4px solid #fff;
}

/* set button(top and bottom of the scrollbar) */
body::-webkit-scrollbar-button {
    display:none;
}
li,ul,p,h1,h2,h3,h4{
  margin:0;
}
</style>