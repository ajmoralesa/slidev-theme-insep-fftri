<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../layoutHelper";
const props = defineProps({
  title: {
    type: String,
  },
  subtitle: {
    type: String,
  },
  imageLeft: {
    type: String,
  },
  imageTopRight: {
    type: String,
  },
  imageBottomRight: {
    type: String,
  },
});
const left = computed(() => handleBackground(props.imageLeft));
const topRight = computed(() => handleBackground(props.imageTopRight));
const bottomRight = computed(() => handleBackground(props.imageBottomRight));
</script>

<template>
  <div class="slidev-layout images-3">
    <slot />
    <div class="grid grid-cols-2 w-full h-96 gap-x-7">
      <div class="ml-14 my-14" :style="left"></div>
      <div class="grid grid-rows-2 w-full h-full gap-y-7">
        <div class="mr-14 mt-14" :style="topRight"></div>
        <div class="mr-14 mb-14" :style="bottomRight"></div>
      </div>
    </div>
  </div>
</template>
