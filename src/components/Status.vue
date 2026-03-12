<template>
  <!-- NOT STARTED -->
  <Badge
    v-if="variant === 1"
    class="flex gap-[10px] border-transparent text-white text-[15px]"
    variant="outline"
    ><div class="w-[17px] h-[17px] bg-[#B0B0B0] rounded-[50%]"></div>
    Not Started</Badge
  >
  <!-- IN PROGRESS -->
  <Badge
    v-if="variant === 2"
    class="flex gap-[10px] border-transparent text-white text-[15px]"
    variant="outline"
    ><div class="w-[17px] h-[17px] bg-[#F2DD3C] rounded-[50%]"></div>
    In Progress</Badge
  >
  <!-- COMPLETED-->
  <Badge
    v-if="variant === 3"
    class="flex gap-[10px] border-transparent text-white text-[15px]"
    variant="outline"
    ><div class="w-[17px] h-[17px] bg-[#37FA68] rounded-[50%]"></div>
    Completed</Badge
  >
</template>

<script setup>
import { Badge } from "@/components/ui/badge";
import { defineProps } from "vue";

defineProps({
  variant: Number,
});
</script>
