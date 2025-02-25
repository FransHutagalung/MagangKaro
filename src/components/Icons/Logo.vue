<template>
  <div
    ref="logoRef"
    class="logo z-4 flex flex-col items-center pt-4"
    :style="{
      backgroundColor: '#ffe3b3',
      height: isScrolled ? '80px' : '110px',
      width: isScrolled ? '80px' : '120px',
      position: 'fixed',
      zIndex: 20,
      left: isScrolled ? '4%' : '45%',
    }"
  >
    <img
      :style="{
        width: isScrolled ? '60px' : '80px',
      }"
      :css="false"
      src="/logofix.png"
      alt=""
    />
    <div
      :style="{
        position: 'absolute',
        width: '0',
        top: isScrolled ? '80px' : '110px',
        zIndex: '4',
        borderTop: isScrolled? '20px solid #ffe3b3' : '50px solid #ffe3b3',
        borderLeft: isScrolled ? '40px solid transparent' : '60px solid transparent',
        borderRight: isScrolled ? '40px solid transparent' : '60px solid transparent',
      }"
      class="triangle"
    ></div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const logoRef = ref(null)
const isScrolled = ref(false)

function handleScroll() {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  handleScroll() // Set posisi awal
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.logo {
  transition: left 0.5s ease;
}

img {
  width: 80px;
  z-index: 10;
}

.triangle {
  position: absolute;
  width: 0;
  top: 110px;
  z-index: 4;
  border-top: 50px solid #ffe3b3;
  border-left: 60px solid transparent;
  border-right: 60px solid transparent;
}
</style>
