<template>
  <div class="work_wrapper peach center-content">
    <div class="mycontainer">
      <h1 class="text-center">FreeLance Work</h1>
      <br>
      <br>
      <div>
        <app-carousel :slides="slides"/>
      </div>
    </div>
  </div>
</template>

<script>
import Carousel from './ui/Carousel.vue';

export default {
  components:{
    appCarousel:Carousel
  },
  data(){
    return {
      slides: [
        {
          id:'1',
          img:'https://firebasestorage.googleapis.com/v0/b/portfolio-b6252.appspot.com/o/Screenshot%20(49).png?alt=media&token=f5c62594-fed0-4cf5-ac13-91056c720e6f',
          desc:`Web app to facilitates the purchase or sale of private securities. Full stack apllication with firebase backend`,
          link:'http://sharesbay.com/'
        },
        {
          id:'2',
          img:'https://firebasestorage.googleapis.com/v0/b/portfolio-b6252.appspot.com/o/Screenshot%20(50).png?alt=media&token=f93ebbd5-9450-4fac-9dd5-900584d77a95',
          desc:`Job Portal with admin panel, email services. Full stack apllication with firebase backend`,
          link:'https://jobs.thewallstreetschool.com/'
        },
        {
          id:'3',
          img:'https://firebasestorage.googleapis.com/v0/b/portfolio-b6252.appspot.com/o/Screenshot%20(52).png?alt=media&token=de0f48f0-7297-4956-81d4-16019d6683fe',
          desc:`Next js server side rendered web app`,
          link:'https://socialrect.com/'
        }

      ]
    }
  }
}
</script>

<style scoped>
.work_wrapper {
  padding: 3.5rem 0;
  background : #24252a;
  min-height:600px;
}
</style>