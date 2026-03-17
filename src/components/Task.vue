<template>
  <div
    class="flex bg-[#585F7A] rounded-[11px] xl:w-[950px] h-[60px] lg:w-[750px] lg:h-[60px] sm:w-[500px] sm:h-[160px] justify-between px-[20px]"
  >
    <ItemTitle class="text-white xl:text-[20px] lg:text-[15px]">{{
      title
    }}</ItemTitle>
    <div
      class="xl:flex lg:flex xl:gap-[50px] lg:gap-[50px] sm:gap-[0px] sm:grid select-none"
    >
      <div class="xl:flex sm:grid lg:flex sm:justify-end">
        <Priority :variant="priority" />
        <Status :variant="status" />
      </div>
      <ItemActions
        class="xl:gap-[20px] lg:gap-[20px] sm:gap-[0px] xl:flex lg:flex sm:grid"
      >
        <p class="text-white xl:text-[15px] lg:text-[15px] lg:text-[10px]">
          {{ date }}
        </p>
        <div class="flex justify-end">
          <button class="cursor-pointer">
            <img src="../assets/eye.svg" alt="viewButton" />
          </button>
          <button class="cursor-pointer">
            <img src="../assets/trash.svg" alt="deleteButton" />
          </button>
        </div>
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
