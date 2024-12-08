<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../layoutHelper.ts";
const props = defineProps({
  background: {
    default: "../public/insep-halle-burlesque.jpg",
  },
});
const style = computed(() => handleBackground(props.background, true));
</script>

<template>
  <div class="slidev-layout cover text-center" :style="style">
    <div class="my-auto w-full">
      <slot />
    </div>
  </div>
</template>
