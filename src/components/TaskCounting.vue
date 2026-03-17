<template>
  <div
    v-if="variant === 1"
    class="h-[40px] px-[12px] rounded-[11px] flex items-center justify-center bg-[#375CFA]/20"
  >
    <p class="xl:text-[24px] lg:text-[20px] text-[#375CFA]">
      TOTAL: {{ counting }}
    </p>
  </div>
  <div
    v-else-if="variant === 2"
    class="h-[40px] px-[12px] rounded-[11px] flex items-center justify-center bg-[#37FA68]/20"
  >
    <p class="xl:text-[24px] lg:text-[20px] text-[#37FA68]">
      SUCCESS: {{ counting }}
    </p>
  </div>
  <div
    v-else-if="variant === 3"
    class="h-[40px] px-[12px] rounded-[11px] flex items-center justify-center bg-[#FA3737]/20"
  >
    <p class="xl:text-[24px] lg:text-[20px] text-[#FA3737]">
      PENDING: {{ counting }}
    </p>
  </div>
</template>

<script setup>
defineProps({
  variant: Number,
  counting: Number,
});
</script>
