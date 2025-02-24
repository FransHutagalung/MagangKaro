<template>
  <div
  style="background-color: #ffe3b3; height: 120px; width: 120px; "
  class=" relative flex flex-col items-center pt-4  ">
    <img
    src="/logofix.png" alt="">
    <div class="triangle"></div>
  </div>
</template>

<script setup lang="ts">
</script>

<style scoped>
img{
  width:  80px;
  z-index: 10;
}

.triangle {
    position: absolute;
    width: 0;
    top: 100px;
    z-index: 8;
    border-top:60px solid #ffe3b3;
    border-left:60px solid transparent;
    border-right:60px solid transparent;
}

</style>
