<script lang="ts" setup>
  import { defineProps } from "vue";

  const props = defineProps({
    label: {
      type: String,
      required: true,
    },
    fieldId: {
      type: String,
      required: true,
    },
    checked: {
      type: Boolean,
    },
  });
</script>

<template>
  <div class="flex flex-row items-center">
    <input
      @input="(event) => $emit('update:checked', event.target.checked)"
      type="checkbox"
      :checked="checked"
      :id="fieldId"
      class="w-4 h-4 rounded mr-2"
    />
    <label
      :for="fieldId"
      class="cursor-pointer select-none"
    >
      {{ label }}
    </label>
  </div>
</template>


