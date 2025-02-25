<template>
  <div
    style="background-color: #26648e; top: 100px; left: 0px"
    ref="listRef"
    class="absolute z-5 w-full h-10 flex "
  >
    <div ref="liRef" class="w-1/2 flex justify-center items-center">
      <ul class="flex   flex-row gap-10 text-white">
        <li>Home</li>
        <li>About</li>
        <li>Contact</li>
      </ul>
    </div>
    <div ref="liRef" class="w-1/2 px-3 flex justify-center items-center">
      <ul class="flex  flex-row gap-10 text-white">
        <li>Forum</li>
        <li>Join</li>
        <li>Contact</li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { animate } from 'motion'
import { ref, onMounted, onUnmounted } from 'vue'

const listRef = ref(null)
const liRef = ref(null)

function handleScroll() {
  if (listRef.value && liRef.value) {
    const scrollY = window.scrollY
    if (scrollY > 50) {
      listRef.value.style.top = '20px'
      listRef.value.style.left = '50%'
      listRef.value.style.width = '50%'
      listRef.value.style.backgroundColor = 'transparent'
      listRef.value.style.flexDirection = 'column'
      liRef.value.style.width = '100%'
      liRef.value.style.justifyContent = 'start'
    } else {
      listRef.value.style.top = '100px'
      listRef.value.style.left = '0px'
      listRef.value.style.width = '100%'
      listRef.value.style.backgroundColor = '#26648e'
      listRef.value.style.flexDirection = 'row'
      liRef.value.style.width = '50%'
      liRef.value.style.justifyContent = 'center'
    }
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)

  handleScroll()

  console.log('Logo element mounted:', listRef.value)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
