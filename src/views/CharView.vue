<script setup>
import { ref, onMounted, onBeforeUnmount, computed } from 'vue'
const image = import.meta.glob('@/assets/char/**/*.webp', { eager: true });
const imageMap = Object.keys(image).reduce((acc, path) => {
  // 提取相对路径（如 'abds/acb.png'）
  const relativePath = path.replace(/^.*\/char\//, '').replace('.webp', '');
  acc[relativePath] = image[path].default; // 存储完整解析路径
  return acc;
}, {});
const images = ref([
  { active: imageMap['a/1'], unactive: imageMap['ua/1'], name: 'Protagonist' },
  { active: imageMap['a/2'], unactive: imageMap['ua/2'], name: 'Yukari' },
  { active: imageMap['a/3'], unactive: imageMap['ua/3'], name: 'Junpei' },
  { active: imageMap['a/4'], unactive: imageMap['ua/4'], name: 'Akihiko' },
  { active: imageMap['a/5'], unactive: imageMap['ua/5'], name: 'Mitsuru' },
  { active: imageMap['a/6'], unactive: imageMap['ua/6'], name: 'Fuuka' },
  { active: imageMap['a/7'], unactive: imageMap['ua/7'], name: 'Koromaru' },
  { active: imageMap['a/8'], unactive: imageMap['ua/8'], name: 'Aigis' },
  { active: imageMap['a/9'], unactive: imageMap['ua/9'], name: 'Ken' },
  { active: imageMap['a/10'], unactive: imageMap['ua/10'], name: 'Shinjiro' }
]);

const scrollContainer = ref(null);
let scrollAmount = 0;
let isScrolling = false;
const smoothScroll = () => {
  const container = scrollContainer.value;
  if (!container) return;
  container.scrollLeft += scrollAmount;
  scrollAmount *= 0.7; // Damping effect
  if (Math.abs(scrollAmount) > 0.5) {
    requestAnimationFrame(smoothScroll);
  } else {
    isScrolling = false;
  }
  updateBackgroundByScroll();
};
const charContainer = ref(null);
const isFullyInView = () => {
  if (!charContainer.value) return false;
  const rect = charContainer.value.getBoundingClientRect();
  const vh = window.innerHeight || document.documentElement.clientHeight;
  // 如果顶部未到视口顶部，或底部未进入视口底部，则视为未完全可见
  return rect.bottom <= vh;
};
const handleScroll = (event) => {
  const container = scrollContainer.value;
  if (!container) return;

  // 如果该区域未完全在视口中，则不阻止默认行为
  if (!isFullyInView()) {
    return;
  }

  const { scrollLeft, scrollWidth, clientWidth } = container;
  const isAtStart = scrollLeft <= 0;
  const isAtEnd = scrollLeft + clientWidth >= scrollWidth;

  if (
    (isAtStart && event.deltaY < 0) ||
    (isAtEnd && event.deltaY > 0)
  ) {
    return;
  }

  // 阻止垂直滚动，启用横向滚动
  event.preventDefault();
  event.stopPropagation();

  scrollAmount += event.deltaY * 0.7;
  if (!isScrolling) {
    isScrolling = true;
    requestAnimationFrame(smoothScroll);
  }
};

const currentIndex = ref(-1);
const currentIndex2 = ref(0);
const bgColors = [
  '#5ba4d7', // 初始背景色（index = -1）
  '#86edfc', // image index 0
  '#fc93ff',
  '#989ffb',
  '#d3dada',
  '#f68ca8',
  '#95f5dc',
  '#f2f4f2',
  '#faf6a6',
  '#faba80',
  '#ce8998'
];
const currentBgColor = computed(() => {
  return bgColors[currentIndex.value + 1] || bgColors[0]; // +1 映射到颜色数组
});
const updateBackgroundByScroll = () => {
  const container = scrollContainer.value;
  if (!container) return;

  const scrollLeft = container.scrollLeft;
  const totalImages = images.value.length;
  const vwToPixels = window.innerWidth * 0.91;
  const adjustedScrollWidth = container.scrollWidth - vwToPixels;
  
  const imageWidth = adjustedScrollWidth / totalImages;

  let index = Math.floor(scrollLeft / imageWidth);

  // 如果还没滚动到第一个 image，设为 -1（初始）
  if (scrollLeft < imageWidth * 0.4) {
    index = -1;
  }

  if (index !== currentIndex.value) {
    currentIndex.value = index;
    if(index != -1) {
      currentIndex2.value = index;
    }
  }
};
</script>

<template>
  <div class="char" :style="{ backgroundColor: currentBgColor }" ref="charContainer">
    <div class="scroll-container" @wheel="handleScroll" ref="scrollContainer">
      <div class="image-wrapper">
        <div class="font">
          <svg fill="#fff" id="_レイヤー_1" data-name="レイヤー 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 747.37 211.14">
            <g><path class="cls-1" d="m1.68,198.79l-1.68-42.96h1.68c11.23,34.54,31.45,51.38,56.16,51.38,22.74,0,44.08-15.44,44.08-42.4s-20.22-37.06-44.36-49.14l-14.04-7.02C23.58,98.83,4.21,85.92,4.21,55.88,4.21,23.87,27.8,0,61.21,0c15.44,0,36.22,5.05,49.7,12.07v33.41h-1.68C98.27,16.29,80.86,3.93,60.09,3.93c-23.59,0-39.31,16-39.31,39.59s18.53,33.69,35.1,42.12l14.04,7.02c24.71,12.35,48.57,25.55,48.57,59.24s-25.83,59.24-64.02,59.24c-16.29,0-39.87-5.05-52.79-12.35Z"></path><path class="cls-1" d="m129.69,195.14c0-8.99,7.3-16.29,16.29-16.29s16,7.3,16,16.29-7.3,16-16,16-16.29-7.3-16.29-16Z"></path><path class="cls-1" d="m318.62,160.6l-6.46,47.17h-141.51v-1.68c19.09,0,20.22-12.63,20.22-33.41V38.47c0-20.78-1.12-33.41-20.22-33.41v-1.68h137.3l3.65,42.12h-1.68c-14.32-32.01-23.59-37.62-54.19-37.62h-40.15v91.25h31.45c25.27,0,30.89-6.74,35.66-27.52h1.68v61.49h-1.68c-4.77-19.94-10.39-29.48-35.66-29.48h-31.45v86.48c0,8.42,2.53,13.2,11.23,13.2h33.13c29.76,0,40.43-5.05,57-42.68h1.68Z"></path><path class="cls-1" d="m333,195.14c0-8.99,7.3-16.29,16.29-16.29s16,7.3,16,16.29-7.3,16-16,16-16.29-7.3-16.29-16Z"></path><path class="cls-1" d="m521.93,160.6l-6.46,47.17h-141.51v-1.68c19.09,0,20.22-12.63,20.22-33.41V38.47c0-20.78-1.12-33.41-20.22-33.41v-1.68h137.3l3.65,42.12h-1.68c-14.32-32.01-23.59-37.62-54.19-37.62h-40.15v91.25h31.45c25.27,0,30.89-6.74,35.66-27.52h1.68v61.49h-1.68c-4.77-19.94-10.39-29.48-35.66-29.48h-31.45v86.48c0,8.42,2.53,13.2,11.23,13.2h33.13c29.76,0,40.43-5.05,57-42.68h1.68Z"></path><path class="cls-1" d="m536.31,195.14c0-8.99,7.3-16.29,16.29-16.29s16,7.3,16,16.29-7.3,16-16,16-16.29-7.3-16.29-16Z"></path><path class="cls-1" d="m587.07,198.79l-1.68-42.96h1.68c11.23,34.54,31.45,51.38,56.16,51.38,22.74,0,44.08-15.44,44.08-42.4s-20.22-37.06-44.36-49.14l-14.04-7.02c-19.94-9.83-39.31-22.74-39.31-52.79,0-32.01,23.59-55.88,57-55.88,15.44,0,36.22,5.05,49.7,12.07v33.41h-1.68c-10.95-29.2-28.36-41.55-49.14-41.55-23.59,0-39.31,16-39.31,39.59s18.53,33.69,35.1,42.12l14.04,7.02c24.71,12.35,48.57,25.55,48.57,59.24s-25.83,59.24-64.02,59.24c-16.29,0-39.87-5.05-52.79-12.35Z"></path><path class="cls-1" d="m715.08,195.14c0-8.99,7.3-16.29,16.29-16.29s16,7.3,16,16.29-7.3,16-16,16-16.29-7.3-16.29-16Z"></path></g>
          </svg>
          <div
            class="fontc"
          >
            <span>An aggregation vigilantly chosen to<br/></span>
            <span style="margin-top:4vh">vanquish the Shadows, will face Destiny.<br/></span>
            <span style="margin-top:4vh">Time won't wait for you, destiny won't change for you.</span>
          </div>
        </div>
        <div 
          class="image"
          v-for="(image, index) in images"
          :key="index"
          :style="{ opacity: currentIndex2 == index ? 1 :0.5 }"
        >
          <div class="imagec">
            <img :key="index" :src="image.active"/>
          </div>
          <span class="name">
            {{ image.name }}
            <span class="arrow"></span>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.char {
  width: 100%;
  height: 100%;
  background-color: #5ba4d7;
  -webkit-user-select: none; /* Chrome, Safari, Opera */
  -moz-user-select: none;    /* Firefox */
  -ms-user-select: none;     /* IE 10+ */
  user-select: none;        /* 标准语法 */
  position: relative;
  z-index: 1;
  transition: all 0.3s ease;
}
.scroll-container {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  z-index: 99;
  overflow: hidden;
}
.image-wrapper {
  margin-top: 8vh;
  display: flex;
  height: 81vh;
  gap: 12vw;
  padding-right: 35vw;
  align-items: center;
}
.font {
  width: 46vw;
  margin-left: 8vw;
  margin-right: 2.5vw;
  display: flex;
  flex-direction: column;
}
.fontc {
  margin-top: 7vh;
  text-align: left;
  font-family: NotoSansJP-Regular;
  color: #ffffff;
  font-size: 1.09vw;
  line-height: 5.5vh;
}
.image {
  width: 29vw;
  height: 81vh;
  position: relative;
  z-index: 999;
}
.imagec {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
}
.imagec img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}
.imagec img:hover {
  transform: scale(1.08);
}
.name {
  position: absolute;
  height: 3vh;
  top: 101%;
  color: #25445a;
  font-size: 0.91vw;
  font-family: NotoSansJP-Regular;
}
.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  left: 115%;
  width: 0.9vw;
  height: 1.8vh;
  background-image: url(/src/assets/char/10185.svg);
  background-size: contain;
  background-repeat: no-repeat;
}
</style>
