<template>
  <div class="home_wrapper">
    <video
      class="video"
     src="https://firebasestorage.googleapis.com/v0/b/portfolio-b6252.appspot.com/o/videoplayback%20(online-video-cutter.com).webm?alt=media&token=8061bde9-e5ba-40e2-bedf-ea5a8602d926" loop autoplay muted></video>
    <div 
      class="glass_container" 
      @mousemove="handleMousemove"
      @mouseenter="animateIn"
      @mouseleave="animateOut">
      <div class="glass" id="glass">
        <div class="text">
          <h2>Hey!!</h2>
          <h2>I'm Aadarsh</h2>
          <h2>Web Developer / Programmer</h2>
        </div>
        <div class="icons">
          <div class="icon" @click="redirect('insta')">
            <font-awesome-icon :icon="['fab', 'instagram']"/>
          </div>
          <div class="icon" @click="redirect('linkedin')">
            <font-awesome-icon :icon="['fab', 'linkedin-in']"/>
          </div>
          <div class="icon" @click="redirect('github')">
            <font-awesome-icon :icon="['fab', 'github']"/>
          </div>
          <div class="icon"  @click="redirect('resume')">
            <font-awesome-icon :icon="['far', 'file-alt']"/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      glass:null,
      container:null,
      text:null,
      icons:null
    }
  },
  mounted(){
    this.glass = document.querySelector('.glass')
    this.container = document.querySelector('.glass_container')
    this.text = document.querySelector('.text')
    this.icons = document.querySelector('.icons')
  },
  methods:{
    handleMousemove(e){
      let xAxis = (window.innerWidth/2 - e.pageX) / 10;
      let yAxis = (window.innerHeight/2 - e.pageY) / 10;

      this.glass.style.transform = `rotateY(${xAxis}deg) rotateX(${yAxis}deg)`
    },
    animateIn(){
      this.glass.style.transition = 'all 0.1s ease';
      this.text.style.transform = 'translateZ(100px)';
    },
    animateOut(){
      this.glass.style.transition = 'all 0.5s ease';
      this.glass.style.transform = `rotateY(0deg) rotateX(0deg)`
      this.text.style.transform = 'translateZ(0px)';
    },
    redirect(to){
      console.log(to)
      let link = ''
      if(to==='insta'){
        link = 'https://www.instagram.com/aadarsh8178/'
      } else if(to==='github') {
        link = 'https://github.com/Aadarsh8178'
      } else if(to==='linkedin') {
        link = 'https://www.linkedin.com/in/aadarsh-verma-9a927a190/'
      } else if(to==='resume'){
        link = 'https://drive.google.com/file/d/1UMVzHqUomaKREUGDiLQxA5q9vf5_V22k/view'
      }
      
      window.open(link)

    }
  }
}
</script>

<style scoped>
.home_wrapper{
  min-height: 100vh;
  min-width:100vw;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index:1;
  position:relative;
  overflow: hidden;
  perspective: 700px;
  background-color: #000000;
background-image: linear-gradient(147deg, #000000 0%, #434343 74%);
}
.video{
 position: fixed;
  right: 0;
  bottom: 0;
  min-width: 100%; 
  min-height: 100%;
}
.glass_container{
  width:45rem;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index:10;
}

.glass{
  z-index:1;
  width:40rem;
  max-height: 400px;
  height: 48vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: rgba(255,255,255,0.13);
  padding:3em;
  border-radius: 1em;
  position:relative;
  backdrop-filter: blur(12px);
  background-clip:padding-box;
  box-shadow: 10px 10px 10px rgba(191, 200, 216, 0.06);
  transform-style: preserve-3d;
  color:white;
}
.glass h2{
  line-height: 50px;
}
.text{
  text-align: center;
  z-index:10;
}
.icons {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width:100%;
  font-size:2rem;
  transition:all 0.3s ease 0s;
  color:#0088a9;
  margin-top:1rem;
}
.icons .icon{
  padding:1rem;
  cursor: pointer;
}
.icons .icon:hover{
  color:rgba(0,136,169,0.8);
}
</style>