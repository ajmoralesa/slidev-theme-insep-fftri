<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../layoutHelper";
const props = defineProps({
  imageLeft: {
    type: String,
  },
  imageCenter: {
    type: String,
  },
  imageRight: {
    type: String,
  },
});
const left = computed(() => handleBackground(props.imageLeft));
const center = computed(() => handleBackground(props.imageCenter));
const right = computed(() => handleBackground(props.imageRight));
</script>

<template>
  <!-- <div class="slidev-layout images-3-bottom">
    <slot />
  </div> -->
  <div class="slidev-layout images-3-bottom">
    <div class="grid grid-rows-2 h-full content-between">
      <div>
        <slot />
      </div>

      <div class="grid grid-cols-3 h-40 w-full h-full gap-x-7 self-end">
        <div :style="left"></div>
        <div :style="center"></div>
        <div :style="right"></div>
      </div>
    </div>
  </div>
</template>
