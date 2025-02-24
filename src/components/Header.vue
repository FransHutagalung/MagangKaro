<template>
  <main style="background-color: #53d2dc" class="fixed flex w-full items-center justify-center bg-blue-300">
    <div class="relative h-26 w-full">
      <!-- <p>ou</p> -->
       <div class="absolute z-4 w-full h-full bg-black"></div>
      <Logo />
    </div>
    <BottomHeader />
  </main>
</template>

<script setup lang="ts">
import Logo from './Icons/Logo.vue'
import BottomHeader from './BottomHeader.vue'
</script>

<style scoped></style>
