<template>
  <div class="flex bg-[#585F7A] rounded-[11px] w-[950px] h-[60px]">
    <Item>
      <ItemContent>
        <ItemTitle class="text-white text-[20px]"
          >Lorem ipsum dolor sit amet</ItemTitle
        >
      </ItemContent>
      <div class="flex">
        <div class="flex">
          <PriorityAndStatus :variant="4" />
          <Status :variant="1" />
        </div>
        <ItemActions>
          <p class="text-white text-[15px]">{{ date }}</p>
          <button>
            <img src="../assets/eye.svg" alt="" />
          </button>
          <button>
            <img src="../assets/trash.svg" alt="" />
          </button>
        </ItemActions>
      </div>
    </Item>
  </div>
</template>

<script setup>
import {
  Item,
  ItemActions,
  ItemContent,
  ItemTitle,
} from "@/components/ui/item";
import PriorityAndStatus from "./Priority.vue";
import Status from "./Status.vue";
import { defineProps } from "vue";

defineProps({
  date: String,
});
</script>
