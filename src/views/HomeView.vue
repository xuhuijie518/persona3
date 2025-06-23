<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import { gsap } from 'gsap';
const startVideoRef = ref(null)
const loopVideoRef = ref(null)

const show = ref(false);
const show2 = ref(false);
const show3 = ref(true);
let intervalId1 = [];

onMounted(() => {
  const startVideo = startVideoRef.value
  const loopVideo = loopVideoRef.value
  // 初始隐藏循环视频
  loopVideo.style.display = 'none'
  // 当开场视频结束时
  startVideo.addEventListener('ended', () => {
    // 隐藏开场视频
    startVideo.style.display = 'none'
    // 显示循环视频
    loopVideo.style.display = 'block'
    // 播放循环视频
    loopVideo.play()
  })
  // 设置循环视频循环播放
  loopVideo.loop = true

  intervalId1.push(setTimeout(() => {
    show.value = !show.value;
  }, 2000));
})

onBeforeUnmount(() => {
  clearInterval(intervalId1);
});



const letters = ref(null);
const letters2 = ref(null);
const imgContainer = ref(null);

const font4 = ref(null);
const imgContainer2 = ref(null);
const imgContainer3 = ref(null);

const letters3 = ref(null);
const font52 = ref(null);
const img51 = ref(null);

const letters4 = ref(null);
const font54 = ref(null);
const img52 = ref(null);
const img53 = ref(null);

const letters5 = ref(null);
const font56 = ref(null);
const img54 = ref(null);
const img55 = ref(null);

const hasAnimated = ref(false);
const hasAnimated2 = ref(false);
const hasAnimated3 = ref(false);
const hasAnimated4 = ref(false);
const hasAnimated5 = ref(false);
let animation;
let animation2;
let animation3;
let animation4;
let animation5;

onMounted(() => {
  if (letters.value) {
    const paths = letters.value.querySelectorAll('path');
    // 初始化动画（默认暂停）
    animation = gsap.from(paths, {
      opacity: 0,
      x: 0,
      y: 50,
      duration: 0.5,
      stagger: 0.1,
      ease: "power2.out",
      paused: true,
    });
  }
  if (letters2.value) {
    const paths = letters2.value.querySelectorAll('path');
    // 初始化动画（默认暂停）
    animation2 = gsap.from(paths, {
      opacity: 0,
      x: 0,
      y: 50,
      duration: 0.5,
      stagger: 0.1,
      ease: "power2.out",
      paused: true,
    });
  }
  if (letters3.value) {
    const paths = letters3.value.querySelectorAll('path');
    // 初始化动画（默认暂停）
    animation3 = gsap.from(paths, {
      opacity: 0,
      x: 0,
      y: 50,
      duration: 0.5,
      stagger: 0.1,
      ease: "power2.out",
      paused: true,
    });
  }
  if (letters4.value) {
    const paths = letters4.value.querySelectorAll('path');
    // 初始化动画（默认暂停）
    animation4 = gsap.from(paths, {
      opacity: 0,
      x: 0,
      y: 50,
      duration: 0.5,
      stagger: 0.1,
      ease: "power2.out",
      paused: true,
    });
  }
  if (letters5.value) {
    const paths = letters5.value.querySelectorAll('path');
    // 初始化动画（默认暂停）
    animation5 = gsap.from(paths, {
      opacity: 0,
      x: 0,
      y: 50,
      duration: 0.5,
      stagger: 0.1,
      ease: "power2.out",
      paused: true,
    });
  }
});

// 仅第一次悬停播放动画
const playAnimationOnce = () => {
  if (!hasAnimated.value && animation && imgContainer.value) {
    animation.play();
    gsap.to(imgContainer.value, {
      opacity: 1,          // 目标透明度
      duration: 2,       // 动画时长（秒）
      ease: "power2.out",  // 缓动效果（平滑结束）
    });
    hasAnimated.value = true;
  }
};

// 仅第一次悬停播放动画
const playAnimationOnce2 = () => {
  if (!hasAnimated2.value) {
    animation2.play();
    gsap.to(imgContainer2.value, {
      opacity: 1,          // 目标透明度
      duration: 2,       // 动画时长（秒）
      ease: "power2.out",  // 缓动效果（平滑结束）
    });
    gsap.fromTo(font4.value, {
      y: 30,
    }, {
      opacity: 1,
      y: 0,
      duration: 1,       // 动画时长（秒）
      ease: "power2.out",  // 缓动效果（平滑结束）
    });
    gsap.fromTo(imgContainer3.value, {
      clipPath: 'inset(100% 0 0 0)' // 初始状态：下侧全部裁剪
    }, {
      opacity: 1,
      clipPath: 'inset(0% 0 0 0)',   // 结束状态：完全不裁剪
      duration: 1.5,
      ease: "power2.out",
    });
    hasAnimated2.value = true;
  }
};

// 仅第一次悬停播放动画
const playAnimationOnce3 = () => {
  if (!hasAnimated3.value) {
    animation3.play();
    gsap.fromTo(font52.value, {
      y: 30,
    }, {
      opacity: 1,
      y: 0,
      duration: 1,       // 动画时长（秒）
      ease: "power2.out",  // 缓动效果（平滑结束）
    });
    gsap.fromTo(img51.value, {
      clipPath: 'inset(100% 0 0 0)' // 初始状态：下侧全部裁剪
    }, {
      opacity: 1,
      clipPath: 'inset(0% 0 0 0)',   // 结束状态：完全不裁剪
      duration: 1.5,
      ease: "power2.out",
    });
    hasAnimated3.value = true;
  }
};

const playAnimationOnce4 = () => {
  if (!hasAnimated4.value) {
    animation4.play();
    gsap.to(img53.value, {
      opacity: 1,          // 目标透明度
      duration: 2,       // 动画时长（秒）
      ease: "power2.out",  // 缓动效果（平滑结束）
    });
    gsap.fromTo(font54.value, {
      y: 30,
    }, {
      opacity: 1,
      y: 0,
      duration: 1,       // 动画时长（秒）
      ease: "power2.out",  // 缓动效果（平滑结束）
    });
    gsap.fromTo(img52.value, {
      clipPath: 'inset(100% 0 0 0)' // 初始状态：下侧全部裁剪
    }, {
      opacity: 1,
      clipPath: 'inset(0% 0 0 0)',   // 结束状态：完全不裁剪
      duration: 1.5,
      ease: "power2.out",
    });
    hasAnimated4.value = true;
  }
};

const playAnimationOnce5 = () => {
  if (!hasAnimated5.value) {
    animation5.play();
    gsap.to(img55.value, {
      opacity: 1,          // 目标透明度
      duration: 2,       // 动画时长（秒）
      ease: "power2.out",  // 缓动效果（平滑结束）
    });
    gsap.fromTo(font56.value, {
      y: 30,
    }, {
      opacity: 1,
      y: 0,
      duration: 1,       // 动画时长（秒）
      ease: "power2.out",  // 缓动效果（平滑结束）
    });
    gsap.fromTo(img54.value, {
      clipPath: 'inset(100% 0 0 0)' // 初始状态：下侧全部裁剪
    }, {
      opacity: 1,
      clipPath: 'inset(0% 0 0 0)',   // 结束状态：完全不裁剪
      duration: 1.5,
      ease: "power2.out",
    });
    hasAnimated5.value = true;
  }
};
</script>

<template>
  <div class="home">
    <div id="page1">
      <div class="videoContainer">
        <video ref="startVideoRef" autoplay muted playsinline class="background-video">
          <source src="/src/assets/home/Persona3_start.mp4" type="video/mp4" />
        </video>
        <video ref="loopVideoRef" loop muted playsinline class="background-video">
          <source src="/src/assets/home/Persona3.mp4" type="video/mp4" />
        </video>
      </div>
      <Transition name="fade">
        <div class="other" v-if="show">
          <div class="img1">
          <img src="/src/assets/home/10011.svg"/>
          </div>
          <div class="scroll">
            SCROLL
          </div>
          <div class="box">
            <div class="line"></div>
          </div>
        </div>
      </Transition>
    </div>
    <div id="page2">
      <div class="font">PLAY TRAILER</div>
      <div class="arrow"></div>
      <div class="page2bg"></div>
      <video autoplay loop muted playsinline class="background-video2">
        <source src="/src/assets/home/videoplayback.mp4" type="video/mp4" />
      </video>
    </div>
    <div id="page3" @mouseenter="playAnimationOnce">
      <div
        class="font2"
      >
        <svg fill="#1d384a" id="_レイヤー_1" data-name="レイヤー 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 455.24 78.41">
          <g ref="letters">
            <path class="cls-1" d="m33.7,39c10.5,1.2,20.4,7.9,20.4,19.4,0,10.8-9.4,18.8-27.1,18.8H0v-.6c6.8,0,7.2-4.5,7.2-11.9V16.9c0-7.4-.4-11.9-7.2-11.9v-.6h25.6c16.6,0,24.7,6.8,24.7,17.1,0,10.9-8.8,15.8-16.6,17.3v.2ZM19.8,6c-2.4,0-3.8,1.2-3.8,3.6v28.9h8c12,0,17-6.4,17-15.5,0-10.5-5.9-17-17.1-17h-4.1Zm24.6,52.1c0-11.2-7.4-18-20-18h-8.4v29.1c0,2.7,0,6.4,8.9,6.4,12.3,0,19.5-6.4,19.5-17.5Z"></path>
            <path class="cls-1" d="m66.21,53.4V16.9c0-7.4-.4-11.9-7.2-11.9v-.6h23.3v.6c-6.8,0-7.2,4.5-7.2,11.9v35.8c0,16.2,5.1,23.3,17.4,23.3s19.4-7.1,19.4-22.8v-30.7c0-9.8-1.6-17.5-8.4-17.5v-.6h18v.6c-6.8,0-7.8,7.7-7.8,17.5v30.7c0,16.9-7.8,25.2-22.9,25.2-16,0-24.6-7.9-24.6-25Z"></path>
            <path class="cls-1" d="m166.7,4.4h16.5v.6c-5.5.5-10.1,8-15.6,18.9l-10.3,20.2v20.6c0,7.4.4,11.9,7.2,11.9v.6h-23.2v-.6c6.8,0,7.2-4.5,7.2-11.9v-18.9l-14.6-28.6c-4.6-8.9-6.5-11.7-9.6-12.2v-.6h22.7v.6c-6,.4-7.5,3.9-4.6,9.5l13.9,27.4,9.5-18.6c5.8-11.5,7.5-17.4.9-18.3v-.6Z"></path>
            <path class="cls-1" d="m256.5,4.4h18.7v.6c-6.8,0-7.8,6.9-7.8,17.5v55.7h-.6L223.6,12.1v48c0,9.6,1.6,16.5,8.9,16.5v.6h-19.5v-.6c7,0,8.8-6.9,8.8-16.5V15.7c0-6.9-2.8-9.9-8.8-10.7v-.6h16l36.6,56.4V22.5c0-10.6-1.5-17.5-9.1-17.5v-.6Z"></path>
            <path class="cls-1" d="m280.77,41c0-22.4,13.1-37.8,32.5-37.8s32.4,14.6,32.4,37.4-13.2,37.8-32.6,37.8-32.3-14.6-32.3-37.4Zm55-.2c0-20.2-8.1-36.2-22.7-36.2s-22.5,15.4-22.5,36.2,8.2,36.2,22.7,36.2,22.5-15.4,22.5-36.2Z"></path>
            <path class="cls-1" d="m421.89,4.4h16.5v.6c-5.1.6-7.7,6.4-11.4,18.7l-16.8,54.5h-.8l-16.3-50.1-18.3,50.1h-.8l-19.1-61c-2.6-8.3-4.9-11.8-9.1-12.2v-.6h23.3v.6c-6.1.4-7.8,3.4-5.9,9.5l15.2,48.7,13.7-38-2.6-8c-2.8-8.4-4.8-11.8-9.3-12.2v-.6h23.3v.6c-6,.4-7.7,3.4-5.8,9.5l15.5,47.8,11.9-39.2c3.6-12.1,4.1-17.5-3.2-18.1v-.6Z"></path>
            <path class="cls-1" d="m443.74,72.7c0-3.2,2.7-5.8,5.8-5.8s5.7,2.6,5.7,5.8-2.6,5.7-5.7,5.7-5.8-2.6-5.8-5.7Zm5.4-14.6c-1.4-17.8-4.5-51.2-4.5-53.4,0-2.4,2.1-4.7,4.9-4.7s4.9,2.4,4.9,4.7-3.1,35.6-4.5,53.4h-.8Z"></path>
          </g>
        </svg>
      </div>
      <div class="img2" ref="imgContainer">
        <a href="">
          <img src="/src/assets/home/10015.webp"/>
        </a>
      </div>
    </div>

    <div id="page4" @mouseenter="playAnimationOnce2">
      <div
        class="font3"
      >
        <svg fill="#1d384a" id="_レイヤー_1" data-name="レイヤー 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 181 76">
          <g ref="letters2">
            <path d="M28.4934 74H0.0933838V73.4C6.89338 73.4 7.29338 68.9 7.29338 61.5V13.7C7.29338 6.3 6.89338 1.8 0.0933838 1.8V1.2H29.0934C51.8934 1.2 64.9934 14.2 64.9934 36.7C64.9934 59.7 50.4934 74 28.4934 74ZM28.8934 72.4C46.7934 72.4 55.0934 58.8 55.0934 37.3C55.0934 17.2 46.5934 2.8 28.3934 2.8H19.8934C17.4934 2.8 16.0934 3.99999 16.0934 6.39999V66C16.0934 70.6 18.6934 72.4 28.8934 72.4Z" fill="#1D384A"></path>
            <path d="M116.967 74H70.8668V73.4C77.6668 73.4 78.0668 68.9 78.0668 61.5V13.7C78.0668 6.3 77.6668 1.8 70.8668 1.8V1.2H94.0668V1.8C87.2668 1.8 86.8668 6.3 86.8668 13.7V67.7C86.8668 70.8 87.7668 72.4 90.7668 72.4H97.7668C108.567 72.4 112.667 70 118.867 56.3H119.467L116.967 74Z" fill="#1D384A"></path>
            <path d="M158.072 75.2C138.672 75.2 124.572 60.2 124.572 37.8C124.572 15.4 138.572 0 158.072 0C168.472 0 175.172 2.99999 179.672 5.39999L180.272 17.5H179.672C175.072 6.6 168.272 1.4 157.872 1.4C143.972 1.4 134.372 16.8 134.372 37.7C134.372 58.3 144.172 73.8 157.872 73.8C168.272 73.8 175.972 68.1 180.272 55.9H180.872L179.272 70.1C174.672 72.4 167.872 75.2 158.072 75.2Z" fill="#1D384A"></path>
          </g>
        </svg>
      </div>
      <div
        class="font4"
         ref="font4"
      >
        These additional content sets will allow you to change your appearance and BGM as you explore Tartarus,<br/> as well as unlock special Personas that you can fuse and use in battle.
      </div>
      <div class="img3" ref="imgContainer3">
        <img src="/src/assets/home/10016.webp"/>
      </div>
      <div class="img4" ref="imgContainer2">
        <a href="https://p3re.jp/en/dlc/">
          <img src="/src/assets/home/10017.webp"/>
        </a>
      </div>
    </div>

    <div id="page5">
      <div class="page51" @mouseenter="playAnimationOnce3"></div>
      <div class="page52" @mouseenter="playAnimationOnce4"></div>
      <div class="page53" @mouseenter="playAnimationOnce5"></div>
      <div
        class="font51"
      >
        <svg fill="#1d384a" id="_レイヤー_1" data-name="レイヤー 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 524.24 79.41">
          <g ref="letters3">
            <path d="M0,78.21v-.6c6.8,0,7.2-4.5,7.2-11.9V17.9c0-7.4-.4-11.9-7.2-11.9v-.6H23.2v.6c-6.8,0-7.2,4.5-7.2,11.9v47.8c0,7.4,.4,11.9,7.2,11.9v.6H0Z"></path>
            <path d="M73.75,67.8c0,6.4,.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-25.4c0-7.6-2.4-12.4-9.4-12.4-4.4,0-9.2,2.2-13.5,5.6v32.2c0,6.4,.3,9.8,4.4,9.8v.6H30.25v-.6c4.1,0,4.4-3.4,4.4-9.8v-29c0-6.4-1.7-8.5-5.1-9.4v-.6l12.8-4h.4v9.8c5.3-5.5,11.6-10,18.3-10,7.8,0,12.7,5.5,12.7,15.6v27.6Z"></path>
            <path d="M114.78,70.1c-4.7,5.9-10.7,9.3-15.9,9.3-7.4,0-11.7-4.1-11.7-12.6V29.5h-5.2v-1.1l1.4-.6c4.9-2.1,8.4-6.1,11.3-15.1h.6v13.1h18.7l-1.4,3.7h-17.3v36.4c0,5.9,2.7,9,7.9,9,4,0,8-2.4,11-5.2l.6,.4Z"></path>
            <path d="M149.67,25.4l-2,8.6h-.6c-2.2-1.5-4.8-2.4-6.9-2.4-2.7,0-5.3,1.5-8,5.3v30.9c0,6.4,.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-29c0-6.4-1.7-8.5-5.1-9.4v-.6l12.8-4h.4v10.7c4.1-6.3,8.5-10.9,13.6-10.9,1.2,0,2.5,.2,3.9,.8Z"></path>
            <path d="M152.57,52.2c0-16.6,10.4-27.6,24.4-27.6s24.1,10.4,24.1,27.2-10.4,27.6-24.3,27.6-24.2-10.4-24.2-27.2Zm39.7-.2c0-14.5-5.4-26-15.5-26s-15.4,10.9-15.4,26,5.5,26,15.6,26,15.3-10.9,15.3-26Z"></path>
            <path d="M252.73,65.9c0,6.4,1.6,8.8,5.1,9.8v.6l-11.1,3.1h-.4l-1.6-9.7c-3.9,5.4-9.1,9.7-16.3,9.7-11.7,0-20-10.9-20-26.4,0-17.1,10.5-28.4,24.4-28.4,4.5,0,8.5,1.3,11.8,3.3V13.2c0-6.4-1.7-8.5-5.1-9.4v-.6l12.8-3.2h.4V65.9Zm-8.1,2.5v-27c0-8.9-4.5-15.4-12.2-15.4-10.2,0-15.3,11.6-15.3,24.4s5.1,24.5,15.3,24.5c5.1,0,9.1-2.9,12.2-6.5Z"></path>
            <path d="M305.7,65.9c0,6.4,1.6,8.8,5.1,9.8v.6l-11.1,3.1h-.4l-1.7-10c-5.3,5.5-11.6,10-18.3,10-7.8,0-12.7-5.5-12.7-15.6v-27.9c0-6.4-1.9-8.2-5.3-9.1v-.6l13-1.4h.4V61.6c0,7.6,2.4,12.4,9.4,12.4,4.4,0,9.2-2.2,13.5-5.5V35.9c0-6.4-1.9-8.2-5.3-9.1v-.6l13-1.4h.4v41.1Z"></path>
            <path d="M316,52.8c0-16.5,10.7-28.2,23.6-28.2,7.1,0,13.5,3.6,16.9,8.5l-4,6h-.6c-2-7.5-5.6-13.1-12.3-13.1-9.6,0-15.1,11-15.1,23.3,0,13.9,5.7,25.1,16.5,25.1,7.2,0,12.7-4.2,15.8-8.7l.6,.4c-3.5,6.1-9.5,13.3-20,13.3-13.3,0-21.4-11.7-21.4-26.6Z"></path>
            <path d="M394.51,70.1c-4.7,5.9-10.7,9.3-15.9,9.3-7.4,0-11.7-4.1-11.7-12.6V29.5h-5.2v-1.1l1.4-.6c4.9-2.1,8.4-6.1,11.3-15.1h.6v13.1h18.7l-1.4,3.7h-17.3v36.4c0,5.9,2.7,9,7.9,9,4,0,8-2.4,11-5.2l.6,.4Z"></path>
            <path d="M399.4,78.21v-.6c4.1,0,4.4-3.4,4.4-9.8v-29c0-6.4-1.7-8.5-5.1-9.4v-.6l12.8-4h.4v43c0,6.4,.3,9.8,4.4,9.8v.6h-16.9Zm1.7-67.5c0-3.1,2.5-5.6,5.7-5.6s5.6,2.5,5.6,5.6-2.5,5.6-5.6,5.6-5.7-2.5-5.7-5.6Z"></path>
            <path d="M421.93,52.2c0-16.6,10.4-27.6,24.4-27.6s24.1,10.4,24.1,27.2-10.4,27.6-24.3,27.6-24.2-10.4-24.2-27.2Zm39.7-.2c0-14.5-5.4-26-15.5-26s-15.4,10.9-15.4,26,5.5,26,15.6,26,15.3-10.9,15.3-26Z"></path>
            <path d="M519.84,67.8c0,6.4,.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-25.4c0-7.6-2.4-12.4-9.4-12.4-4.4,0-9.2,2.2-13.5,5.6v32.2c0,6.4,.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-29c0-6.4-1.7-8.5-5.1-9.4v-.6l12.8-4h.4v9.8c5.3-5.5,11.6-10,18.3-10,7.8,0,12.7,5.5,12.7,15.6v27.6Z"></path>
          </g>
        </svg>
      </div>
      <div
        class="font52 font5content"
         ref="font52"
      >
        <span>Life doesn't always go as planned, and you—as the protagonist—transfer into <br/>Gekkoukan High School, located at the center of the man-made Tatsumi Port <br/>Island only for a terrifying creature to attack your dorm.<br/></span>
        <span style="margin-top:4vh">In the midst of chaos, you awaken to your Persona—a powerful force that can be <br/>used to fight back.</span>
        <span style="margin-top:4vh">A group of others who share this power recruit you into their Specialized <br/>Extracurricular Excecution Squad (S.E.E.S.), and so begins your journey to uncover <br/>the mysteries behind these incidents...</span>
      </div>
      <div class="img51" ref="img51">
          <img src="/src/assets/home/10186.png"/>
      </div>

      <div
        class="font53"
      >
        <svg fill="#1d384a" id="_レイヤー_1" data-name="レイヤー 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 353.21 74">
          <g ref="letters4">
            <path class="cls-1" d="M47.6,0l1.2,15h-.6C43.1,3.6,39.8,1.6,29,1.6h-13V36.1h11.2c9,0,11-2.4,12.7-9.8h.6v21.9h-.6c-1.7-7.1-3.7-10.5-12.7-10.5h-11.2v22.6c0,7.4,.4,11.9,7.2,11.9v.6H0v-.6c6.8,0,7.2-4.5,7.2-11.9V12.5C7.2,5.1,6.8,.6,0,.6V0H47.6Z"></path><path class="cls-1" d="M93,60.9c-3.5,6-9.6,13.1-20.2,13.1-13.3,0-21.4-11.7-21.4-26.6,0-16.5,10.7-28.2,23.6-28.2,10.5,0,18.5,7.4,17.9,20H60.2c-.2,1.5-.3,3-.3,4.5,0,14.2,5.6,25.4,16.8,25.4,6.9,0,12.5-4,15.7-8.6l.6,.4Zm-32.6-23.3h23.9c.8-10.3-2.2-17-9.8-17s-12.6,7.7-14.1,17Z"></path><path class="cls-1" d="M142.61,67.3c-1.6,3-4.9,6.7-9.4,6.7-5,0-6.1-4.9-6.3-8.5-4.1,5.1-10.1,8.5-15.8,8.5-6.8,0-11.6-4.3-11.6-10.5,0-7.2,5.5-12.1,17.6-15.6l9.5-2.7v-7.7c0-2.9,0-13.8-10.1-13.8-6.7,0-11.6,4.7-14.7,10.7l-.6-.3c1.6-5.5,7.4-14.9,19-14.9,9.7,0,14.4,6.7,14.4,16.1v26.4c0,4.1,.2,7.5,3.3,7.5,2.1,0,3.5-1.5,4.1-2.3l.6,.4Zm-16-2.8v-17.8l-7.1,2.3c-9.2,3-11.9,6.1-11.9,11.9,0,5.3,3.4,8.6,8.1,8.6,4,0,8.2-2.6,10.9-5Z"></path><path class="cls-1" d="M177.89,64.7c-4.7,5.9-10.7,9.3-15.9,9.3-7.4,0-11.7-4.1-11.7-12.6V24.1h-5.2v-1.1l1.4-.6c4.9-2.1,8.4-6.1,11.3-15.1h.6v13.1h18.7l-1.4,3.7h-17.3V60.5c0,5.9,2.7,9,7.9,9,4,0,8-2.4,11-5.2l.6,.4Z"></path><path class="cls-1" d="M226.68,60.5c0,6.4,1.6,8.8,5.1,9.8v.6l-11.1,3.1h-.4l-1.7-10c-5.3,5.5-11.6,10-18.3,10-7.8,0-12.7-5.5-12.7-15.6V30.5c0-6.4-1.9-8.2-5.3-9.1v-.6l13-1.4h.4V56.2c0,7.6,2.4,12.4,9.4,12.4,4.4,0,9.2-2.2,13.5-5.5V30.5c0-6.4-1.9-8.2-5.3-9.1v-.6l13-1.4h.4V60.5Z"></path><path class="cls-1" d="M268.47,20l-2,8.6h-.6c-2.2-1.5-4.8-2.4-6.9-2.4-2.7,0-5.3,1.5-8,5.3v30.9c0,6.4,.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-29c0-6.4-1.7-8.5-5.1-9.4v-.6l12.8-4h.4v10.7c4.1-6.3,8.5-10.9,13.6-10.9,1.2,0,2.5,.2,3.9,.8Z"></path><path class="cls-1" d="M312.8,60.9c-3.5,6-9.6,13.1-20.2,13.1-13.3,0-21.4-11.7-21.4-26.6,0-16.5,10.7-28.2,23.6-28.2,10.5,0,18.5,7.4,17.9,20h-32.7c-.2,1.5-.3,3-.3,4.5,0,14.2,5.6,25.4,16.8,25.4,6.9,0,12.5-4,15.7-8.6l.6,.4Zm-32.6-23.3h23.9c.8-10.3-2.2-17-9.8-17s-12.6,7.7-14.1,17Z"></path><path class="cls-1" d="M320.41,70.8l-.8-12.4h.6c3.7,8.9,8.3,14.2,16,14.2,5.9,0,11.4-3.1,11.4-9.9,0-6-4.2-8.2-11.9-12.4l-3.8-2c-5.3-2.9-10.9-6.3-10.9-14.5,0-9.1,7-14.6,16.5-14.6,4,0,9.5,.9,13.3,3v10.2h-.6c-2.5-7.4-7.6-11.8-13.7-11.8s-9.9,3.7-9.9,9.1c0,5.7,4.4,8.5,9.3,11l3.7,2c7.2,3.8,13.6,6.9,13.6,15.8,0,9.4-7.5,15.5-18.3,15.5-5.2,0-10.9-1.3-14.5-3.2Z"></path>
          </g>
        </svg>
      </div>
      <div
        class="font54 font5content"
         ref="font54"
      >
        <span>The new and improved version of Persona 3 preserves the story and characters fans <br/>know and love while introducing new quality-of-life mechanics and a complete <br/>graphical overhaul.<br/></span>
        <span style="margin-top:4vh">Experience what made this game leave such an impact, now better than ever.</span>
      </div>
      <div class="img52" ref="img52">
        <img src="/src/assets/home/10075.webp"/>
      </div>
      <div class="img53" ref="img53">
        <a href="">
          <img src="/src/assets/home/10018.webp"/>
        </a>
      </div>

      <div
        class="font55"
      >
        <svg fill="#1d384a" id="_レイヤー_1" data-name="レイヤー 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 541.47 97.41">
          <g ref="letters5">
            <path class="cls-1" d="m0,37.8C0,15.4,14.1,0,33.5,0c11,0,18.2,2.8,23,5.4v11.7h-.6C50.6,6.2,44.4,1.4,33.4,1.4c-14,0-23.6,15.4-23.6,36.3s9.1,36.1,23.8,36.1c8.6,0,15.4-3.6,15.4-9.4v-11c0-7.4-.6-11.1-6.4-11.5v-.6h18.4v.6c-3,.4-3.2,4.1-3.2,11.5v14.6c-5.6,3.8-14.3,7.2-24.5,7.2C13.1,75.21,0,59.7,0,37.8Z"></path><path class="cls-1" d="m107.15,68.5c-1.6,3-4.9,6.7-9.4,6.7-5,0-6.1-4.9-6.3-8.5-4.1,5.1-10.1,8.5-15.8,8.5-6.8,0-11.6-4.3-11.6-10.5,0-7.2,5.5-12.1,17.6-15.6l9.5-2.7v-7.7c0-2.9,0-13.8-10.1-13.8-6.7,0-11.6,4.7-14.7,10.7l-.6-.3c1.6-5.5,7.4-14.9,19-14.9,9.7,0,14.4,6.7,14.4,16.1v26.4c0,4.1.2,7.5,3.3,7.5,2.1,0,3.5-1.5,4.1-2.3l.6.4Zm-16-2.8v-17.8l-7.1,2.3c-9.2,3-11.9,6.1-11.9,11.9,0,5.3,3.4,8.6,8.1,8.6,4,0,8.2-2.6,10.9-5Z"></path><path class="cls-1" d="m181.9,63.6c0,6.4.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-25.4c0-7.6-2.4-12.3-9.4-12.3-4.4,0-9,2.1-12.8,5.6.3,1.4.4,2.9.4,4.5v27.6c0,6.4.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-25.4c0-7.6-2.4-12.3-9.3-12.3-4.4,0-8.8,2.1-12.5,5.4v32.3c0,6.4.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-29c0-6.4-1.7-8.5-5.1-9.4v-.6l12.8-4h.4v9.6c4.8-5.4,10.6-9.8,17.2-9.8s10.7,3.6,12.2,10.2c4.8-5.6,11-10.2,17.7-10.2,7.8,0,12.7,5.5,12.7,15.6v27.6Z"></path><path class="cls-1" d="m231.57,62.1c-3.5,6-9.6,13.1-20.2,13.1-13.3,0-21.4-11.7-21.4-26.6,0-16.5,10.7-28.2,23.6-28.2,10.5,0,18.5,7.4,17.9,20h-32.7c-.2,1.5-.3,3-.3,4.5,0,14.2,5.6,25.4,16.8,25.4,6.9,0,12.5-4,15.7-8.6l.6.4Zm-32.6-23.3h23.9c.8-10.3-2.2-17-9.8-17s-12.6,7.7-14.1,17Z"></path><path class="cls-1" d="m261.27,70.8l-.6-15.3h.6c4,12.3,11.2,18.3,20,18.3,8.1,0,15.7-5.5,15.7-15.1s-7.2-13.2-15.8-17.5l-5-2.5c-7.1-3.5-14-8.1-14-18.8,0-11.4,8.4-19.9,20.3-19.9,5.5,0,12.9,1.8,17.7,4.3v11.9h-.6c-3.9-10.4-10.1-14.8-17.5-14.8-8.4,0-14,5.7-14,14.1s6.6,12,12.5,15l5,2.5c8.8,4.4,17.3,9.1,17.3,21.1s-9.2,21.1-22.8,21.1c-5.8,0-14.2-1.8-18.8-4.4Z"></path><path class="cls-1" d="m334.4,21.6h13.9v.6c-3.5.6-5.6,4.5-9.8,15.6l-17,44.6c-4,10.4-9.3,15-15.4,15-1.8,0-3.3-.2-4.9-.7l.8-7.2h.6c6,5.2,13.1,3.6,16.8-6.4l3.7-9.8-15-39.8c-2.9-7.7-4.5-10.7-7.9-11.3v-.6h18.3v.6c-4.5.4-4.6,3.6-2.8,8.6l11.6,31.4,9.5-25c4-10.5,2.4-14.5-2.4-15v-.6Z"></path><path class="cls-1" d="m349.2,72l-.8-12.4h.6c3.7,8.9,8.3,14.2,16,14.2,5.9,0,11.4-3.1,11.4-9.9,0-6-4.2-8.2-11.9-12.4l-3.8-2c-5.3-2.9-10.9-6.3-10.9-14.5,0-9.1,7-14.6,16.5-14.6,4,0,9.5.9,13.3,3v10.2h-.6c-2.5-7.4-7.6-11.8-13.7-11.8s-9.9,3.7-9.9,9.1c0,5.7,4.4,8.5,9.3,11l3.7,2c7.2,3.8,13.6,6.9,13.6,15.8,0,9.4-7.5,15.5-18.3,15.5-5.2,0-10.9-1.3-14.5-3.2Z"></path><path class="cls-1" d="m418.07,65.9c-4.7,5.9-10.7,9.3-15.9,9.3-7.4,0-11.7-4.1-11.7-12.6V25.3h-5.2v-1.1l1.4-.6c4.9-2.1,8.4-6.1,11.3-15.1h.6v13.1h18.7l-1.4,3.7h-17.3v36.4c0,5.9,2.7,9,7.9,9,4,0,8-2.4,11-5.2l.6.4Z"></path><path class="cls-1" d="m461.26,62.1c-3.5,6-9.6,13.1-20.2,13.1-13.3,0-21.4-11.7-21.4-26.6,0-16.5,10.7-28.2,23.6-28.2,10.5,0,18.5,7.4,17.9,20h-32.7c-.2,1.5-.3,3-.3,4.5,0,14.2,5.6,25.4,16.8,25.4,6.9,0,12.5-4,15.7-8.6l.6.4Zm-32.6-23.3h23.9c.8-10.3-2.2-17-9.8-17s-12.6,7.7-14.1,17Z"></path><path class="cls-1" d="m537.07,63.6c0,6.4.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-25.4c0-7.6-2.4-12.3-9.4-12.3-4.4,0-9,2.1-12.8,5.6.3,1.4.4,2.9.4,4.5v27.6c0,6.4.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-25.4c0-7.6-2.4-12.3-9.3-12.3-4.4,0-8.8,2.1-12.5,5.4v32.3c0,6.4.3,9.8,4.4,9.8v.6h-16.9v-.6c4.1,0,4.4-3.4,4.4-9.8v-29c0-6.4-1.7-8.5-5.1-9.4v-.6l12.8-4h.4v9.6c4.8-5.4,10.6-9.8,17.2-9.8s10.7,3.6,12.2,10.2c4.8-5.6,11-10.2,17.7-10.2,7.8,0,12.7,5.5,12.7,15.6v27.6Z"></path>
          </g>
        </svg>
      </div>
      <div
        class="font56 font5content"
         ref="font56"
      >
        <span>The Persona 3 experience becomes even more enjoyable while retaining its <br/>originality.<br/></span>
        <span style="margin-top:3vh">A more exhilarating battle system and new graphics and gimmicks make <br/>Tartarus easier to explore. Dormitory life and community have also legitimately <br/>evolved!</span>
      </div>
      <div class="img54" ref="img54">
          <img src="/src/assets/home/10050.webp"/>
      </div>
      <div class="img55" ref="img55">
        <a href="">
          <img src="/src/assets/home/10019.webp"/>
        </a>
      </div>

      <div class="dec"></div>
      <div
        class="font58"
         ref="font58"
      >
        <span>Dark Hour<br/></span>
        <span style="margin-top:3vh">While I breathe, I hope<br/></span>
        <span style="margin-top:3vh">Rise again</span>
      </div>
      <div
        class="font57"
      >
        <svg fill="none" stroke='#abc0d4' stroke-miterlimit="10" stroke-width='2px' id="_レイヤー_1" data-name="レイヤー 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1913.8 376.9">
          <g ref="letters6">
            <path class="cls-1 svg-elem-1" d="M255.7,374.9v3.1c-6.6,1-28,2-41.8,2c-33.6,0-42.8-18.3-105.9-153.3c-9.7-19.4-20.4-22.9-36.7-22.9H44.8v110.5c0,37.7,1.5,60.6,36.2,60.6v3.1H-36.7v-3.1C-2,374.9,0,351.9,0,314.3V70.8c0-37.7-2-60.6-36.7-60.6V7.1H89.6c78.4,0,123.8,38.7,123.8,97.8c0,50.4-38.7,81.5-83,93.7v1c14.8,9.2,27,30.6,38.2,52.5C218,347.4,228.7,365.7,255.7,374.9L255.7,374.9z M44.8,195.6H83c55.5,0,83-32.1,83-87.6c0-53.5-25.5-92.7-82.5-92.7H64.2c-12.2,0-19.4,6.1-19.4,18.3C44.8,33.6,44.8,195.6,44.8,195.6z"></path><path class="cls-1 svg-elem-2" d="M562.9,292.4l-11.7,85.6H294.5v-3.1c34.6,0,36.7-22.9,36.7-60.6V70.8c0-37.7-2-60.6-36.7-60.6V7.1h249.1l6.6,76.4h-3.1c-26-58.1-42.8-68.3-98.3-68.3H376v165.5h57c45.8,0,56-12.2,64.7-49.9h3.1v111.5h-3.1C489,206.3,478.8,189,433,189h-57v156.9c0,15.3,4.6,23.9,20.4,23.9h60.1c54,0,73.3-9.2,103.4-77.4L562.9,292.4L562.9,292.4z"></path><path class="cls-1 svg-elem-3" d="M603.1,377.9v-3.1c34.6,0,36.7-22.9,36.7-60.6V70.8c0-37.7-2-60.6-36.7-60.6V7.1h118.2v3.1c-34.6,0-36.7,22.9-36.7,60.6v275.1c0,15.8,4.6,23.9,19.9,23.9h35.7c55,0,75.9-12.2,107.5-82h3.1l-12.7,90.2L603.1,377.9L603.1,377.9z"></path><path class="cls-1 svg-elem-4" d="M890.4,193.5C890.4,79.4,957.2,1,1056,1c99.8,0,165,74.4,165,190.5c0,114.1-67.2,192.5-166,192.5C955.1,384,890.4,309.7,890.4,193.5L890.4,193.5z M1170.6,192.5c0-102.9-41.3-184.4-115.6-184.4S940.4,86.6,940.4,192.5c0,102.9,41.8,184.4,115.6,184.4C1130.4,376.9,1170.6,298.5,1170.6,192.5L1170.6,192.5z"></path><path class="cls-1 svg-elem-5" d="M1495.2,312.7c15.3,42.8,25,60.1,46.4,62.1v3.1h-116.1v-3.1c28.5-2,37.7-18.8,27-49.9l-27-76.9h-120.2l-12.2,34.6c-20.9,60.1-21.4,89.1,15.3,92.2v3.1h-84v-3.1c24.4-2.5,37.7-33.6,59.1-95.2L1381.7,2h4.1L1495.2,312.7z M1309.3,235.8h112.1l-56-160.4L1309.3,235.8L1309.3,235.8z"></path><path class="cls-1 svg-elem-6" d="M1582.2,377.9v-3.1c34.6,0,36.7-22.9,36.7-60.6V70.8c0-37.7-2-60.6-36.7-60.6V7.1h147.7c116.1,0,182.9,66.2,182.9,180.8c0,117.2-73.9,190-185.9,190L1582.2,377.9L1582.2,377.9z M1862.3,191c0-102.4-43.3-175.7-136-175.7H1683c-12.2,0-19.4,6.1-19.4,18.3v303.6c0,23.4,13.2,32.6,65.2,32.6C1820.1,369.8,1862.3,300.5,1862.3,191L1862.3,191z"></path>
          </g>
        </svg>
      </div>
    </div>
  </div>
</template>

<style scoped>
.home {
  width: 100%;
  height: 100%;
  background-color: #fff;
  z-index: 5;
  overflow-x: hidden;
  overflow-y: scroll;
  -webkit-user-select: none; /* Chrome, Safari, Opera */
  -moz-user-select: none;    /* Firefox */
  -ms-user-select: none;     /* IE 10+ */
  user-select: none;        /* 标准语法 */
}
img {
  width: 100%;
  height: auto;
}
#page1 {
  width: 100vw;
  height: 100vh;
  position: relative;
  z-index: 1;
}
.videoContainer{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: -2;
}
.other {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease-in-out;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.background-video {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.img1 {
  position: absolute;
  right: 20.9vw;
  top: 17.15vw;
  width: 19.7vw;
}
.scroll {
  position: absolute;
  bottom: 5.4vw;
  left: 50%;
  transform: translateX(-50%);
  font-family: Syncopate-Bold;
  font-size: 0.65vw;
  color: #fff;
}
.box {
  width: 3vw;
  height: 3vw;
  position: absolute;
  bottom: 2vw;
  left: 50%;
  transform: translateX(-50%);
  overflow: hidden;
}
.line {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 1px;
  height: 60%;
  background: rgb(255, 255, 255);
  animation: moveDown 1.2s linear infinite;
}

@keyframes moveDown {
  0% {
    top: -20%;
    opacity: 1;
  }
  100% {
    top: 100%; /* 移动到方框底部 */
    opacity: 0.2;
  }
}

#page2 {
  width: 100vw;
  height: 32.6vh;
  position: relative;
  z-index: 1;
  cursor: pointer;
}
.background-video2 {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -2;
}
.page2bg {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: #dce9f5;
  z-index: -1;
  opacity: 1;
  transition: all 0.5s ease;
}
.font {
  font-family: Syncopate-Bold;
  font-size: 1.05vw;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-60%, -50%);
  color: #1d384a;
  transition: all 0.5s ease;
}
.arrow {
  position: absolute;
  top: 50%;
  right: 44%;
  transform: translateY(-50%);
  width: 1.2vw;
  height: 1.2vw;
  background-color: #1d384a;
  mask-image: url('/src/assets/home/10002.svg');
  mask-size: contain;
  mask-repeat: no-repeat;
  transition: all 0.5s ease;
}
#page2:hover .font {
  color: #fff;
}
#page2:hover .arrow {
  background-color: #fff;
  right: 43%;
}
#page2:hover .page2bg {
  opacity: 0.5;
  background-color: #3826fbce;
}

#page3 {
  width: 100vw;
  height: 81vh;
  position: relative;
  z-index: 1;
  background-color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.font2 {
  margin-top: 5vh;
  width: 29vw;
}
.img2 {
  width: 29vw;
  margin-top: 16vh;
  opacity: 0
}


#page4 {
  width: 100vw;
  height: 100vh;
  position: relative;
  z-index: 1;
  background-color: #e5eef6;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.font3 {
  width: 11vw;
}
.font4 {
  width: 50vw;
  height: 8vh;
  color: #667b8a;
  font-size: 0.97vw;
  line-height: 4vh;
  font-family: NotoSansJP-Regular;
  margin-top: 4.5vh;
  overflow: hidden;
  opacity: 0;
}
.img3 {
  width: 67vw;
  margin-top: 7vh;
  opacity: 0;
}
.img4 {
  width: 29vw;
  margin-top: 9.2vh;
  opacity: 0;
}

#page5 {
  width: 100vw;
  height: 321vh;
  position: relative;
  z-index: 1;
  background-color: #c0d5e8;
}
.page51 {
  position: absolute;
  width: 100vw;
  top: 0;
  height: 98vh;
}
.page52 {
  position: absolute;
  width: 100vw;
  top: 98vh;
  height: 82vh;
}
.page53 {
  position: absolute;
  width: 100vw;
  top: 180vh;
  height: 98vh;
}
.font51 {
  position: absolute;
  top: 34vh;
  left: 8vw;
  width: 27.2vw;
}
.font5content {
  font-size: 0.97vw;
  line-height: 4vh;
  font-family: NotoSansJP-Regular;
  text-align: left;
}
.font52 {
  position: absolute;
  top: 48vh;
  left: 8vw;
  display: flex;
  flex-direction: column;
  opacity: 0;
}
.img51 {
  position: absolute;
  right: -11.5vw;
  top: 26.3vh;
  width: 64.5vw;
  height: 57.4vh;
  overflow: hidden;
  opacity: 0;
}
.img51 img {
  transform: translateX(-7vw);
}
.img52 {
  position: absolute;
  left: -1vw;
  top: 98.5vh;
  width: 53vw;
  height: 57.8vh;
  overflow: hidden;
  opacity: 0;
}
.font53 {
  position: absolute;
  top: 102.6vh;
  right: 24vw;
  width: 18.5vw;
}
.font54 {
  position: absolute;
  top: 119.7vh;
  right: 5.2vw;
  display: flex;
  flex-direction: column;
  opacity: 0;
}
.img53 {
  position: absolute;
  right: 17.6vw;
  top: 148.5vh;
  width: 25vw;
  height: 57.4vh;
  overflow: hidden;
  opacity: 0;
}

.font55 {
  position: absolute;
  top: 184.6vh;
  left: 9.3vw;
  width: 28vw;
}
.font56 {
  position: absolute;
  top: 201vh;
  left: 9.3vw;
  display: flex;
  flex-direction: column;
  opacity: 0;
}
.img54 {
  position: absolute;
  right: 0vw;
  top: 180vh;
  width: 53vw;
  height: 57.4vh;
  overflow: hidden;
  opacity: 0;
}
.img55 {
  position: absolute;
  left: 9vw;
  top: 228vh;
  width: 25vw;
  height: 57.4vh;
  overflow: hidden;
  opacity: 0;
}

.font57 {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100vw;
}
.font58 {
  position: absolute;
  bottom: 54vh;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  font-family: NotoSansJP-Regular;
  color: #496375;
  font-size: 0.85vw;
}
.dec {
  width: 1px;
  height: 6.5vh;
  background-color: #000000;
  position: absolute;
  bottom: 64vh;
  left: 50%;
  transform: translateX(-50%);
}
</style>