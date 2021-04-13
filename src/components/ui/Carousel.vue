<template>
  <div class="slider d-flex">
    <div 
      :key="slide.id" 
      v-for="(slide,ind) in slides" 
      :style="{transform:'translateX('+X+'%)',cursor:'pointer'}"
      class="slide"
      @click="openSite(slide.link)"
      >
      <div class="card"  :style="'transform:scaleY('+(ind==currentSlide?'1':'0.5')+')'">
        <img :src="slide.img" alt="img">
        <div class="text">
          {{slide.desc}}
        </div>
      </div>
    </div>
    <div class="left" @click="slide(1)">
      <font-awesome-icon :icon="['fas', 'chevron-left']"/>
    </div>
    <div class="right" @click="slide(-1)">
      <font-awesome-icon :icon="['fas', 'chevron-right']"/>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    width:String,
    height:String,
    slides:Array,
    simple:Boolean
  },
  data(){
    return {
      X:-100,
      currentSlide:1,
      right:true,
      interval:null
    }
  },
  methods:{
    openSite(link) {
      window.open(link)
    },
    slide(by,within) {
      if(!within&&this.interval){
        clearInterval(this.interval)
        this.interval = null;
        setTimeout(()=>{
          this.autoSlide()
        },10000)
      }
      if(this.X == 0 && by > 0){
        return;
      }
      if(this.X == -100*(this.slides.length-1) && by < 0){
        return;
      }
      this.X = this.X + (by*100);
      if(by>0)
        this.currentSlide--;
      else
        this.currentSlide++;
    },
    autoSlide(){
      this.interval = setInterval(()=>{
      if(this.currentSlide==0){
        this.right = true;
      }
      if(this.currentSlide==this.slides.length-1){
        this.right=false;
      }
      if(this.right){
        this.slide(-1,true);
      } else {
        this.slide(1,true);
      }
    },3000)
    }
    
  },
  
  mounted(){
    this.autoSlide()
  }
  
}
</script>

<style scoped>
.slider{
  overflow: hidden;
  position: relative;
  padding:0 80px;
  display: flex;
  height:600px;
}
.progress{
  position: absolute;
  top:0;
  left:0;
  width:calc(100% - 174px);
  margin:0 87px;
  height:10px;
  z-index:100;
  background:rgba(0,0,0,0.1);
  border-radius: 0;
}
.progress-bar{
  background: rgba(73, 156, 189, 0.8);
  border-radius: 0;
}
.slide {
  position: relative;
  min-width:100%;
  height:100%;
  padding:0 8px;
  display: flex;
  justify-content:center;
  align-items: center;
  transition: 0.4s ease-in-out;
}
.slide img {
  width:100%;
  object-fit: cover;
  border-radius: 10px;
}

.card{
  display: flex;
  height: 100%;
	width: 100%;
	background-color: rgba(255, 255, 255, 0.06);
	backdrop-filter: blur(12px);
	position: absolute;
	box-shadow: 20px 20px 25px rgba(0, 0, 0, 0.2);
	border: 2px solid rgba(255, 255, 255, 0.06);
	border-radius: 10px;
  transform:scaleY(0.5);
  transition: 0.4s ease-in-out;
  padding:4rem;
  margin:1rem;
}
.slide .text{
  position: absolute;
  top:50%;
  left:50%;
  transform: translate(-50%,-50%);
  background: rgba(0,0,0,0.8);
  padding:1rem;
  text-align:center;
}

.left,.right{
  position: absolute;
  z-index: 10;
  top:0;
  left:0;
  width:80px;
  height:100%;
  display: flex;
  justify-content: center;
  align-items: center;
  transition:all 0.1s ease;
}
.right{
  left:100%;
  transform: translateX(-100%);
}
.left:hover,.right:hover{
  background: rgba(0,0,0,0.2);
}
.icons{
  position: absolute;
  z-index:100;
  top:85%;
  left:50%;
  transform:translateX(-50%);
  font-size:2.5rem;
}
.correct,.wrong{
  margin:0 1rem;
}
.correct{
  color:rgb(145, 221, 145);
}
.wrong{
  color:rgb(197, 44, 44);
}
@media only screen and (max-width: 768px) {
  .slider{
    padding:0;
  }
  .progress{
    width:100%;
    margin:0;
  }
  .slide{
    padding:0;
  }
}
</style>