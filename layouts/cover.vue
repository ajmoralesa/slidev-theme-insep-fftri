<script setup lang="ts">
// No props or computed values needed anymore
</script>

<template>
  <div
    class="slidev-layout cover text-center"
    style="
      background-image: url(../public/coverFFTRI.png);
      background-size: contain;
      background-repeat: no-repeat;
      background-position: center;
    "
  >
    <div class="my-auto w-full text-center text-light-50">
      <slot />
    </div>
  </div>
</template>
