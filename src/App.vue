<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref, reactive, onMounted, onUnmounted, onBeforeUnmount, computed, inject } from 'vue'
import HomeView from './views/HomeView.vue';
const show = ref(false);
const show2 = ref(false);
const show3 = ref(true);
let intervalId1 = [];
onMounted(()=>{
  intervalId1.push(setTimeout(() => {
    show.value = !show.value;
  }, 0));
  intervalId1.push(setTimeout(() => {
    show3.value = !show3.value;
  }, 5000));
  intervalId1.push(setTimeout(() => {
    show2.value = !show2.value;
  }, 5400));
})

onBeforeUnmount(() => {
  clearInterval(intervalId1);
});

</script>

<template>
  <div class="main">
    <Transition name="nested">
      <div class="boll" v-if="show">
        <div class="water w1"></div>
        <div class="water w2"></div>
        <div class="water"></div>
        <div class="wbg"></div>
      </div>
    </Transition>
    <Transition name="fade">
      <div class="mainword" v-if="show3">
        <div class="mainword1">
          Memento Mori
        </div>
        <div class="mainword2">
          Remember, You Will Die.<br/>
          Time never waits.<br/>
          It delivers all equally to the same end.
        </div>
      </div>
    </Transition>
    <div class="content" v-if="show2">
      <HomeView/>
    </div>
  </div>
</template>

<style>
@font-face {  
  font-family: 'Syncopate-Bold'; 
  src: url('/src/assets/main/Syncopate-Bold.ttf') format('truetype');
}
@font-face {  
  font-family: 'Urbanist'; 
  src: url('/src/assets/main/Urbanist-VariableFont_wght.ttf') format('truetype');
}
@font-face {  
  font-family: 'NotoSansJP-Regular'; 
  src: url('/src/assets/main/NotoSansJP-Regular.otf') format('opentype');
}
@font-face {  
  font-family: 'lato'; 
  src: url('/src/assets/main/lato.ttf') format('truetype');
}
.main {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background-color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
}

.boll {
  position: fixed;
  bottom: -150vh;
  height: 150vh;
  width: 100vw;
  background-color: #ffffff;
  overflow: hidden;
  z-index: 10;
}
.water {
  background: url(/src/assets/main/wave.png) repeat-x;
  position: absolute;
  height: 10%;
  width: 100%;
  top: 0;
  -webkit-animation: move_wave 4s linear infinite;
  animation: move_wave 4s linear infinite;
}
.wbg {
  position: absolute;
  height: 91%;
  width: 100%;
  top: 9%;
  background-color: #029eeb;
}
.w1 {
  opacity: .5;
  background-position: 120px 10px;
  -webkit-animation: move_wave 10s linear infinite;
  animation: move_wave 10s linear infinite;
}
.w2 {
  opacity: .3;
  background-position: 60px 0;
  -webkit-animation: move_wave 8s linear infinite;
  animation: move_wave 8s linear infinite;
}
@-webkit-keyframes move_wave {
  0% {
    background-position: 0 0
  }
  to {
    background-position: 532px 0
  }
}
@keyframes move_wave {
  0% {
    background-position: 0 0
  }
  to {
    background-position: 532px 0
  }
}

.nested-enter-active,
.nested-leave-active {
  transition: all 4s ease-in-out;
}
.nested-enter-from,
.nested-leave-to {
  transform: translateY(-100%);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease-in-out;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}


.mainword {
  width: 25vw;
  height: 10vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  z-index: -1;
}
.mainword1 {
  font-size: 2.7vw;
  font-family: Georgia;
}
.mainword2 {
  font-size: 0.58vw;
  font-family: NotoSansJP-Regular;
}

.content {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 5;
}
</style>
