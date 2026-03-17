<template>
  <div class="flex">
    <Item>
      <ItemContent class="xl:w-[1000px] xl:grid lg:flex lg:w-[800px]">
        <div class="flex justify-between">
          <ItemTitle
            class="cursor-default select-none text-[#B0B0B0] text-[20px]"
          >
            Enter a new To-Do
          </ItemTitle>
          <button class="cursor-pointer" @click="handleClick">
            <img
              class="w-[33px] h-[33px]"
              src="../assets/square-rounded-plus.svg"
              alt="addIcon"
            />
          </button>
        </div>
        <div
          class="xl:w-[1000px] h-[3px] bg-[#585F7A] lg:w-[800px] sm:w-[500px]"
        ></div>
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
