<template>
  <div class="exp_wrapper" id="experience">
    <h1 class="mycontainer" style="margin:auto">Experience</h1>
    <div
      class="exp_card0"
      @mouseenter="animations[0].play()"
      @mouseleave="animations[0].reverse()"
      @click="openSite('https://zedblox.com/')"
    >
      <h1>ZedBlox Logitech</h1>
      <p>
        Integrated map services from google and mapbox ,made style component based SVG
        structure.Worked With React , Redux , Bootstrap , MaterialUI ,Google
        Maps ,Mapbox ,Styled Component
      </p>
    </div>
    <div
      class="exp_card1"
      @mouseenter="animations[1].play()"
      @mouseleave="animations[1].reverse()"
      @click="openSite('https://www.casamelhor.in')"
    >
      <h1>Casa Melhor</h1>
      <p>
          Implemented Vuejs app with dynamic page flow controlled from backend.
          Utilised Vue-router,axios and made generic components.
          Made an iframe based customizable widget
      </p>
    </div>
    <div
      class="exp_card2"
      @mouseenter="animations[2].play()"
      @mouseleave="animations[2].reverse()"
    >
      <h1>Spiritual Syntax</h1>
      <p>
        Implemented a nextjs server side rendered web app from scratch in just 3 days.
        Build a dashboard with multiple user profile to facilitate content on a
        production app.
        Made generic forms based on configuration file.
      </p>
    </div>
  </div>
</template>

<script>
import { TimelineMax, Back,gsap } from "gsap/dist/gsap";
import { CSSRulePlugin } from "gsap/CSSRulePlugin";

gsap.registerPlugin(CSSRulePlugin);

export default {
  data() {
    return {
      animations: [],
    };
  },
  methods:{
    openSite(link) {
      window.open(link)
    }
  },
  mounted() {
    for (let i = 0; i < 3; i++) {
      var rule = CSSRulePlugin.getRule(`.exp_card${i}::before`);
      var rule2 = CSSRulePlugin.getRule(`.exp_card${i}::after`);

      if(i==1){
        rule = CSSRulePlugin.getRule(`.exp_card${i}::after`);
        rule2 = CSSRulePlugin.getRule(`.exp_card${i}::before`);
      }      
      var tl = new TimelineMax({
        defaults: { ease: "power2.inOut" },
        paused: true,
      });

      tl.to(rule, {
        width: "100%",
      });
      tl.to(
        rule2,
        {
          width: "100%",
        },
        "-=.3"
      );
      tl.to(
        `.exp_card${i} h1`,
        {
          color: "white",
        },
        "-=.7"
      );
      tl.to(
        `.exp_card${i} p`,
        {
          clipPath: "circle(140% at 0% 100%)",
          transform: "translateX(0)",
          ease: Back.easeOut.config(4),
        },
        "-=.3"
      );
      this.animations.push(tl);
    }
  },
};
</script>

<style>
.exp_wrapper {
  min-height: 100vh;
  position: relative;
  display: grid;
  place-content: center;
  width: 100vw;
  background: linear-gradient(
    to right,
    #431357 0%,
    #431357 50%,
    #601a7e 50%,
    #53186d 100%
  );
  padding: 3rem 0;
  color:#F8CEEC;
}
.exp_card1,
.exp_card2,
.exp_card0 {
  z-index: 1;
  width: 28%;
  min-width: 400px;
  margin: 5rem auto;
  padding: 3em;
  cursor: pointer;
  position: relative;
  color: #F8CEEC;
  transform: translateX(-150px);
}

.exp_card1{
  transform: translateX(130px);
}

.exp_card0:before,
.exp_card0:after {
  content: "";
  position: absolute;
  min-height: 300px;
  width: 34%;
  background: #24252a;
  top: 0;
  right: 0;
  z-index: -2;
}
.exp_card1:before,
.exp_card1:after {
  content: "";
  position: absolute;
  min-height: 300px;
  width: 0;
  background: #1da4c2;
  top: 0;
  right: 0;
  z-index: -1;
}

.exp_card2:before,
.exp_card2:after {
  content: "";
  position: absolute;
  min-height: 300px;
  width: 34%;
  background: #24252a;
  top: 0;
  right: 0;
  z-index: -2;
}
.exp_card0::after {
  width: 0;
  background: #1da4c2;
  left: 0;
  z-index: -1;
}
.exp_card1::after {
  width: 34%;
  background: #24252a;
  left: 0;
  z-index: -2;
}
.exp_card2::after {
  width: 0;
  background: #1da4c2;
  left: 0;
  z-index: -1;
}
.exp_card1 h1,
.exp_card2 h1,
.exp_card0 h1 {
  margin: 0;
}

.exp_card1 p,
.exp_card2 p,
.exp_card0 p {
  clip-path: circle(0 at 100% 0);
  color: white;
  font-size: 0.9em;
  line-height: 1.6em;
  margin: 0;
  padding: 1.5em 0 0 3em;
  position: relative;
  transform: translateX(50px);
}
.exp_card1 p::before,
.exp_card2 p::before,
.exp_card0 p::before {
  content: "";
  position: absolute;
  height: 80%;
  top: 2em;
  left: 0;
  width: 5px;
  background: #151d44;
}
</style>
