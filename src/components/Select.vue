<template>
  <div>
    <select
      class="border border-[#EBEBEB] rounded-[10px] p-[2px] w-full p-[10px]"
    >
      <option :value="select.value" v-for="select in select">
        {{ select.option }}
      </option>
    </select>
  </div>
</template>

<script setup>
defineProps({
  select: Array,
});
</script>
