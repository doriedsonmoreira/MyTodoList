<template>
  <div
    class="w-full max-w-md bg-white p-[40px] rounded-[11px] fixed shadow-lg plce-self-center"
  >
    <form>
      <FieldGroup>
        <FieldSet>
          <div class="flex w-full justify-between items-center">
            <FieldLegend class="text-[20px] text-[#585F7A]"
              >Create Task</FieldLegend
            >
            <button class="cursor-pointer" @click="handleClick">
              <img src="../assets/square-rounded-x.svg" alt="" />
            </button>
          </div>
          <FieldGroup>
            <Field>
              <FieldLabel> Tittle</FieldLabel>
              <Input
                placeholder="Task tittle here"
                class="text-[#B0B0B0]"
                required
              />
            </Field>
            <Field>
              <FieldLabel> Description</FieldLabel>
              <Textarea placeholder="Description here" required> </Textarea>
            </Field>
            <Field>
              <FieldLabel> Date </FieldLabel>
              <input
                type="date"
                class="text-[#807A78] border border-[#EBEBEB] p-[5px] rounded-[10px] shadow"
                required
              />
            </Field>
            <Field>
              <FieldLabel> Priority </FieldLabel>
              <Select :select="priority" />
            </Field>
            <Field>
              <FieldLabel> Status: </FieldLabel>
              <Select :select="status" />
            </Field>
            <Field>
              <FieldLabel> Tags </FieldLabel>
              <Input placeholder="Tags here" required />
            </Field>
          </FieldGroup>
        </FieldSet>

        <Field orientation="vertical">
          <Button type="submit" class="bg-[#37FA68]"> Create </Button>
        </Field>
      </FieldGroup>
    </form>
  </div>
</template>

<script setup>
import { Button } from "@/components/ui/button";
import {
  Field,
  FieldDescription,
  FieldGroup,
  FieldLabel,
  FieldLegend,
  FieldSeparator,
  FieldSet,
} from "@/components/ui/field";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import { components } from "reka-ui/constant";
import export_default from "reka-ui/resolver";
import Select from "./Select.vue";

const priority = [
  { value: "low", option: "Low Priority" },
  { value: "medium", option: "Medium Priority" },
  { value: "high", option: "High Priority" },
  { value: "criticl", option: "Critical Priority" },
];
const status = [
  { value: "nStarted", option: "Not Started" },
  { value: "iProgress", option: "In Progress" },
  { value: "completed", option: "Completed" },
];

const emit = defineEmits("clickedCloseCreateTask");

function handleClick() {
  emit("clickedCloseCreateTask");
}
</script>
