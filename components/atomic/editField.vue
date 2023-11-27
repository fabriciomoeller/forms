<template>
  <div>
        <label class="text-blue-700 text-sm"> {{ label }} </label>
        <input 
            :type="type" 
            v-model="model"
            @input="$emit('update:modelValue', $event.target.value)"
            class="relative py-2 pr-10 pl-3 w-full text-left bg-white rounded-lg shadow-md cursor-default focus:outline-none focus-visible:border-indigo-500 focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75 focus-visible:ring-offset-2 focus-visible:ring-offset-blue-500 sm:text-sm"
        >
    </div>
</template>

<script setup lang="ts">

  import { defineProps, defineEmits } from "vue";

  interface Props {
    label: string;
    modelValue: string;
    type: string;
  }

  const { modelValue, type = 'number' } = defineProps<Props>();

  const emit = defineEmits(["update:modelValue"]);

</script>

