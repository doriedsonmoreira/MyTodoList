<template>
  <Badge
    v-if="variant === 'Not Started'"
    class="flex gap-[10px] border-transparent text-white xl:text-[15px] lg:text-[10px]"
    variant="outline"
  >
    <div
      class="w-[17px] h-[17px] bg-[#B0B0B0] rounded-[50%] xl:text-[15px] lg:text-[10px]"
    ></div>
    Not Started
  </Badge>
  <Badge
    v-else-if="variant === 'In Progress'"
    class="flex gap-[10px] border-transparent text-white xl:text-[15px] lg:text-[10px]"
    variant="outline"
  >
    <div class="w-[17px] h-[17px] bg-[#F2DD3C] rounded-[50%]"></div>
    In Progress
  </Badge>
  <Badge
    v-else-if="variant === 'Completed'"
    class="flex gap-[10px] border-transparent text-white xl:text-[15px] lg:text-[10px]"
    variant="outline"
  >
    <div class="w-[17px] h-[17px] bg-[#37FA68] rounded-[50%]"></div>
    Completed
  </Badge>
</template>

<script setup>
import { Badge } from "@/components/ui/badge";
import { defineProps } from "vue";

defineProps({
  variant: String,
});
</script>
