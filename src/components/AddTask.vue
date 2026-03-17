<template>
  <div class="flex">
    <Item>
      <ItemContent class="w-[1000px] grid">
        <div class="flex justify-between">
          <ItemTitle
            class="cursor-default select-none text-[#B0B0B0] text-[20px]"
            >Enter a new To-Do</ItemTitle
          >
          <button class="cursor-pointer" @click="handleClick">
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
import { Item, ItemContent, ItemTitle } from "@/components/ui/item";

const emit = defineEmits(["clickedAddTask"]);

function handleClick() {
  emit("clickedAddTask");
}
</script>
