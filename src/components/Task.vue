<template>
  <div
    class="flex bg-[#585F7A] rounded-[11px] w-[950px] h-[60px] justify-between px-[20px]"
  >
    <ItemTitle class="text-white text-[20px]">{{ title }}</ItemTitle>
    <div class="flex gap-[50px] select-none">
      <div class="flex">
        <Priority :variant="priority" />
        <Status :variant="status" />
      </div>
      <ItemActions class="gap-[20px]">
        <p class="text-white text-[15px]">{{ date }}</p>
        <button class="cursor-pointer">
          <img src="../assets/eye.svg" alt="viewButton" />
        </button>
        <button class="cursor-pointer">
          <img src="../assets/trash.svg" alt="deleteButton" />
        </button>
      </ItemActions>
    </div>
  </div>
</template>

<script setup>
import { ItemActions, ItemTitle } from "@/components/ui/item";
import Priority from "./Priority.vue";
import Status from "./Status.vue";
import { defineProps } from "vue";

defineProps({
  title: String,
  date: String,
  priority: String,
  status: String,
});
</script>
