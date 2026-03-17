<template>
  <section
    class="bg-[#7B37FA] h-screen row-auto content-center justify-items-center"
  >
    <ModalAddTask
      v-if="showCreateTask"
      @clickedCloseCreateTask="closeCreateTask"
      @taskCreated="addTaskToList"
    />

    <div
      class="p-[65px] grid rounded-[11px] bg-white w-[1200px] h-[800px] justify-items-center items-center"
    >
      <h1 class="text-[35px] text-[#585F7A]">MY TODO-LIST</h1>
      <div class="flex gap-[275px]">
        <TaskCounting :variant="1" :counting="tasks.length" />
        <TaskCounting
          :variant="2"
          :counting="tasks.filter((t) => t.status === 'Completed').length"
        />
        <TaskCounting
          :variant="3"
          :counting="tasks.filter((t) => t.status !== 'Completed').length"
        />
      </div>
      <AddTask @clickedAddTask="addTask" />
      <div class="grid gap-[15px]">
        <Task
          v-for="task in tasks"
          :key="task.id"
          :title="task.title"
          :date="task.dueDate"
          :priority="task.priority"
          :status="task.status"
        />
      </div>
      <div>
        <Button
          @click="deleteAllTasks"
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
import { ref, onMounted } from "vue";
import AddTask from "./AddTask.vue";
import ModalAddTask from "./ModalAddTask.vue";
import Task from "./Task.vue";
import TaskCounting from "./TaskCounting.vue";
import Button from "./ui/button/Button.vue";
import { api } from "@/services/api";

const showCreateTask = ref(false);
const tasks = ref([]);

function addTask() {
  showCreateTask.value = true;
}

function closeCreateTask() {
  showCreateTask.value = false;
}

function addTaskToList(newTask) {
  tasks.value.push(newTask);
  tasks.value.unshift(newTask);
  showCreateTask.value = false;
}

onMounted(async () => {
  try {
    const response = await api.get("/fake-api/todos");
    tasks.value = response.data;
  } catch (error) {
    console.error("Error fetching tasks:", error);
  }
});

function deleteAllTasks() {
  if (confirm("Are you sure you want to delete ALL tsks?")) {
    tasks.value = [];
    alert("All tasks have been cleared!");
  }
}
</script>
