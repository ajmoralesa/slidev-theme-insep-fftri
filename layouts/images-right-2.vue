<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../layoutHelper";
const props = defineProps({
  imageTop: {
    type: String,
  },
  imageBottom: {
    type: String,
  },
});
const left = computed(() => handleBackground(props.imageTop));
const bottom = computed(() => handleBackground(props.imageBottom));
</script>

<template>
  <div class="slidev-layout images-right-2">
    <div class="grid grid-cols-2 h-full w-full justify-end">
      <div>
        <slot />
      </div>

      <div class="grid grid-rows-2 h-full w-70 gap-y-7 place-self-center">
        <div :style="left"></div>
        <div :style="bottom"></div>
      </div>
    </div>
  </div>
</template>
