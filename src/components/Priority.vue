<template>
  <Badge
    v-if="variant === 'Low'"
    class="flex gap-[10px] border-transparent text-white xl:text-[15px] lg:text-[10px]"
    variant="outline"
  >
    <div class="w-[17px] h-[17px] bg-[#B0B0B0] rounded-[50%]"></div>
    Low Priority
  </Badge>
  <Badge
    v-else-if="variant === 'Medium'"
    class="flex gap-[10px] border-transparent text-white xl:text-[15px] lg:text-[10px]"
    variant="outline"
  >
    <div class="w-[17px] h-[17px] bg-[#F2DD3C] rounded-[50%]"></div>
    Medium Priority
  </Badge>
  <Badge
    v-else-if="variant === 'High'"
    class="flex gap-[10px] border-transparent text-white xl:text-[15px] lg:text-[10px]"
    variant="outline"
  >
    <div class="w-[17px] h-[17px] bg-[#FF7300] rounded-[50%]"></div>
    High Priority
  </Badge>
  <Badge
    v-else-if="variant === 'Critical'"
    class="flex gap-[10px] border-transparent text-white xl:text-[15px] lg:text-[10px]"
    variant="outline"
  >
    <div class="w-[17px] h-[17px] bg-[#FF0000] rounded-[50%]"></div>
    Critical Priority
  </Badge>
</template>

<script setup>
import { Badge } from "@/components/ui/badge";
import { defineProps } from "vue";

defineProps({
  variant: String,
});
</script>
