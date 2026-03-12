<template>
  <!-- LOW -->
  <Badge
    v-if="variant === 1"
    class="flex gap-[10px] border-transparent text-white text-[15px]"
    variant="outline"
    ><div class="w-[17px] h-[17px] bg-[#B0B0B0] rounded-[50%]"></div>
    Low Priority</Badge
  >
  <!-- MEDIUM -->
  <Badge
    v-if="variant === 2"
    class="flex gap-[10px] border-transparent text-white text-[15px]"
    variant="outline"
    ><div class="w-[17px] h-[17px] bg-[#F2DD3C] rounded-[50%]"></div>
    Medium Priority</Badge
  >
  <!-- HIGH -->
  <Badge
    v-if="variant === 3"
    class="flex gap-[10px] border-transparent text-white text-[15px]"
    variant="outline"
    ><div class="w-[17px] h-[17px] bg-[#FF7300] rounded-[50%]"></div>
    High Priority</Badge
  >
  <!-- CRITICAL -->
  <Badge
    v-if="variant === 4"
    class="flex gap-[10px] border-transparent text-white text-[15px]"
    variant="outline"
    ><div class="w-[17px] h-[17px] bg-[#FF0000] rounded-[50%]"></div>
    Critical Priority</Badge
  >
</template>

<script setup>
import { Badge } from "@/components/ui/badge";
import { defineProps } from "vue";

defineProps({
  variant: Number,
});
</script>
