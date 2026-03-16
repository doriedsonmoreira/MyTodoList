<template>
  <section
    class="bg-[#7B37FA] h-screen row-auto content-center justify-items-center"
  >
    <ModalAddTask v-if="showCreateTask" />

    <div
      class="p-[65px] grid rounded-[11px] bg-white w-[1200px] h-[800px] justify-items-center items-center"
    >
      <h1 class="text-[35px] text-[#585F7A]">MY TODO-LIST</h1>
      <div class="flex gap-[275px]">
        <TaskCounting :variant="1" counting="0" />
        <TaskCounting :variant="2" counting="0" />
        <TaskCounting :variant="3" counting="0" />
      </div>
      <AddTask />
      <div class="grid gap-[15px]">
        <Task date="12-03-2026" :priority="1" :status="1" />
        <Task date="12-03-2026" :priority="2" :status="2" />
        <Task date="12-03-2026" :priority="3" :status="3" />
        <Task date="12-03-2026" :priority="4" :status="3" />
      </div>
      <div>
        <Button
          variant="outline"
          class="bg-[#FA3737] text-white text-[20px] p-[11px] border-transparent w-[200px] h-[50px]"
        >
          Delete All Tasks
        </Button>
      </div>
    </div>
  </section>
</template>

<script setup>
import AddTask from "./AddTask.vue";
import ModalAddTask from "./ModalAddTask.vue";
import Task from "./Task.vue";
import TaskCounting from "./TaskCounting.vue";
import Button from "./ui/button/Button.vue";

const showCreateTask = false;
</script>
