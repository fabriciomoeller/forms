<template>
  <div>
        <label :for="label" class="pl-2 block "> {{ label }} </label>
        <input 
            type="string" 
            v-model="model"
            @input="$emit('update:modelValue', $event.target.value)"
            class="py-2 text-left bg-white rounded-lg shadow-md cursor-default 
                   focus:outline-none focus-visible:border-indigo-500 focus-visible:ring-2 focus-visible:ring-white 
                   focus-visible:ring-opacity-75 focus-visible:ring-offset-2 focus-visible:ring-offset-blue-500 
                   focus:shadow-none "
        >

    </div>
</template>

<script setup lang="ts">

  import { defineProps, defineEmits } from "vue";

  interface Props {
    label: string;
    modelValue: string;
  }

  const { modelValue, type = 'number' } = defineProps<Props>();

  const emit = defineEmits(["update:modelValue"]);

</script>

