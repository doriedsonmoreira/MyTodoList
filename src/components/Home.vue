<template>
  <section
    class="bg-[#7B37FA] h-screen row-auto content-center justify-items-center"
  >
    <div
      class="rounded-[11px] bg-white w-[1200px] h-[800px] justify-items-center"
    >
      <h1 class="text-[35px] text-[#585F7A]">MY TODO-LIST</h1>
      <div class="flex">
        <TaskCounting :variant="1" counting="0" />
        <TaskCounting :variant="2" counting="0" />
        <TaskCounting :variant="3" counting="0" />
      </div>
      <AddTask />
    </div>
  </section>
</template>

<script setup>
import AddTask from "./AddTask.vue";
import TaskCounting from "./TaskCounting.vue";
</script>
