<template>
  <div>
    <select
      class="border border-[#EBEBEB] rounded-[10px] p-[10px] w-full"
      :value="modelValue"
      @change="$emit('update:modelValue', $event.target.value)"
    >
      <option v-for="item in select" :key="item.value" :value="item.value">
        {{ item.option }}
      </option>
    </select>
  </div>
</template>

<script setup>
defineProps({
  select: Array,
  modelValue: String,
});
const emit = defineEmits(["update:modelValue"]);
</script>
