<template>
  <div
    class="w-full max-w-md bg-white p-[40px] rounded-[11px] fixed shadow-lg top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"
  >
    <form @submit.prevent="createTask">
      <FieldGroup>
        <FieldSet>
          <div class="flex w-full justify-between items-center">
            <FieldLegend class="text-[20px] text-[#585F7A]">
              Create Task
            </FieldLegend>
            <button type="button" class="cursor-pointer" @click="handleClick">
              <img src="../assets/square-rounded-x.svg" alt="close" />
            </button>
          </div>
          <FieldGroup>
            <Field>
              <FieldLabel>Title</FieldLabel>
              <Input
                v-model="task.title"
                placeholder="Task title here"
                required
              />
            </Field>
            <Field>
              <FieldLabel>Description</FieldLabel>
              <Textarea
                v-model="task.description"
                placeholder="Description here"
                required
              />
            </Field>
            <Field>
              <FieldLabel>Date</FieldLabel>
              <input
                v-model="task.date"
                type="date"
                class="text-[#807A78] border border-[#EBEBEB] p-[5px] rounded-[10px] shadow"
                required
              />
            </Field>
            <Field>
              <FieldLabel>Priority</FieldLabel>
              <Select v-model="task.priority" :select="priority" />
            </Field>
            <Field>
              <FieldLabel>Status</FieldLabel>
              <Select v-model="task.status" :select="status" />
            </Field>
            <Field>
              <FieldLabel>Tags</FieldLabel>
              <Input
                v-model="task.tags"
                placeholder="Comma separated tags"
                required
              />
            </Field>
          </FieldGroup>
        </FieldSet>
        <Field orientation="vertical">
          <Button type="submit" class="bg-[#37FA68]">Create</Button>
        </Field>
      </FieldGroup>
    </form>
  </div>
</template>

<script setup>
import { reactive } from "vue";
import { api } from "@/services/api";
import { Button } from "@/components/ui/button";
import {
  Field,
  FieldGroup,
  FieldLabel,
  FieldLegend,
  FieldSet,
} from "@/components/ui/field";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import Select from "./Select.vue";

const emit = defineEmits(["clickedCloseCreateTask", "taskCreated"]);

const priority = [
  { value: "Low", option: "Low Priority" },
  { value: "Medium", option: "Medium Priority" },
  { value: "High", option: "High Priority" },
  { value: "Critical", option: "Critical Priority" },
];

const status = [
  { value: "Not Started", option: "Not Started" },
  { value: "In Progress", option: "In Progress" },
  { value: "Completed", option: "Completed" },
];

const task = reactive({
  title: "",
  description: "",
  date: "",
  priority: "",
  status: "",
  tags: "",
});

function handleClick() {
  emit("clickedCloseCreateTask");
}

async function createTask() {
  try {
    const body = {
      title: task.title,
      description: task.description,
      dueDate: task.date,
      priority: task.priority,
      status: task.status,
      tags: task.tags.split(",").map((tag) => tag.trim()),
    };
    const response = await api.post("/fake-api/todos", body);
    alert("Task createded successfully", response.data);
    emit("taskCreated", response.data);
    emit("clickedCloseCreateTask");

    Object.assign(task, {
      title: "",
      description: "",
      date: "",
      priority: "",
      status: "",
      tags: "",
    });
  } catch (error) {
    console.error("Error creating task:", error);
  }
}
</script>
