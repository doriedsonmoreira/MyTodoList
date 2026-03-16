<template>
  <div class="flex">
    <Item>
      <ItemContent class="w-[1000px] grid">
        <div class="flex justify-between">
          <ItemTitle
            class="cursor-default select-none text-[#B0B0B0] text-[20px]"
            >Enter a new To-Do</ItemTitle
          >
          <button class="cursor-pointer" @click="showCreateTask = true">
            <img
              class="w-[33px] h-[33px]"
              src="../assets/square-rounded-plus.svg"
              alt="addIcon"
            />
          </button>
        </div>
        <div class="w-[1000px] h-[3px] bg-[#585F7A]"></div>
      </ItemContent>
    </Item>
  </div>
</template>

<script setup>
import {
  Item,
  ItemActions,
  ItemContent,
  ItemDescription,
  ItemMedia,
  ItemTitle,
} from "@/components/ui/item";

import Home from "./Home.vue";
</script>
