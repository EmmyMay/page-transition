<template>
<div>
 <div ref="cover" class="cover">
   <div ref="coverbg" class="coverbg"></div>
 </div>
  <router-view v-slot="slotProps">
    <transition name="route"  @enter=" enter" @before-enter = "beforeEnter" @leave="leave" :css="false"  >
      <component :is="slotProps.Component"></component>
    </transition>
  </router-view>
</div>
</template>

<script>
import gsap from 'gsap';

export default {

  data () {
    return {
      
    }
  },
  methods: {

    beforeEnter(el){
      let cover = this.$refs.coverbg;    
      
     
    },
  
    enter(el, done){
      let cover = this.$refs.coverbg;
      let tl = gsap.timeline({ onComplete: ()=>{
          // el.style.opacity = 1   
          // cover.style.transform = "translateX(0%)"
          done();
          console.log("LeftOncomplete");
          
        }});
        let progress = tl.progress();
        
      
      tl.fromTo(cover, {        
        duration: .1,
        x: "-100%" ,
         onStart: ()=>{
          el.style.opacity = 0;
        }
        
       
             
      }, {
        x: "0%"
      })
      .to(cover, {   
        delay: .5,     
        duration: .6,
        x: "+=100%",
        ease: "back.out(1.7)"
       
             
      })
      
        .to(el, {
        opacity: 1,
        duration: .5
      }, "-=.8")
     
      
    
   
   
      
    },
    leave(){
      console.log("leftOnLeave");
    }
  
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: transparent;
  /* position: absolute; */
  
 
}

.cover{
  position: absolute;
  top: 0;
  height: 100vh;
  width: 100vw; 
  background-color: transparent;
  pointer-events: none;
  z-index: 10;  
  bottom: 0;
  overflow: hidden;
  left: 0;
}
.coverbg{
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: pink;
  transform: translateX(-100%);
}


</style>
