<template>
  <div
    class="px-[12px] rounded-[11px] content-center justify-items-center bg-[#375CFA]/20 width-"
    v-if="variant === 1"
  >
    <p class="text-[24px] text-[#375CFA]">TOTAL: {{ counting }}</p>
  </div>
  <div
    class="px-[12px] rounded-[11px] content-center justify-items-center bg-[#37FA68]/20 width-"
    v-else-if="variant === 2"
  >
    <p class="text-[24px] text-[#37FA68]">SUCCESS: {{ counting }}</p>
  </div>
  <div
    class="px-[12px] rounded-[11px] content-center justify-items-center bg-[#FA3737]/20 width-"
    v-else-if="variant === 3"
  >
    <p class="text-[24px] text-[#FA3737]">PENDING: {{ counting }}</p>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  variant: Number,
  counting: Number,
});
</script>
