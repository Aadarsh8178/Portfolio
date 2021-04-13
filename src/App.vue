<template>
  <div id="app">
    <app-navbar></app-navbar>
    <app-home></app-home>  
    <app-experience></app-experience> 
    <app-my-work></app-my-work>
  </div>
</template>

<script>
import Navbar from './components/DesNavbar.vue';
import Home from './components/Home.vue';
import Experience from './components/Experience.vue';
import MyWork from './components/MyWork.vue';

export default {
  components:{
    appNavbar:Navbar,
    appHome:Home,
    appExperience:Experience,
    appMyWork:MyWork
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
  scroll-behavior: smooth;
}
#app{
  position: relative;
  width: 100%;
  min-height: 100vh; 
  
  /* background-image: linear-gradient(147deg, #923cb5 0%, #211727 74%); */
  font-family: 'Montserrat', sans-serif;
  overflow-x: hidden;
}
body {
  overflow: overlay;
  
}
li,ul,p,h1,h2,h3,h4{
  margin:0;
}
::-webkit-scrollbar {
  width: 10px;
  height: 10px;
}

::-webkit-scrollbar-thumb {
  background: transparent;
}
::-webkit-scrollbar-thumb:hover {
  background: rgba(90, 90, 90);
}
::-webkit-scrollbar-track {
  background: transparent;
}
::-webkit-scrollbar-track:hover {
  background: rgba(0,0,0,0.2);
}
.mycontainer {
  width:90%;
  max-width: 1200px;
}
.pt-5{
  padding-top: 2.5rem;
}
.text-left{
  text-align: left;
}
.text-center{
  text-align: center;
}
.center-content{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.peach{
  color: #F8CEEC;
}
</style>