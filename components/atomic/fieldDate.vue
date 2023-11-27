<template>
  <div>
        <label class="pl-2 block "> {{ label }} </label>
        <input 
            type="date"
            :value="modelValue"
            @input="$emit('update:modelValue', $event.target.value)"
            class="py-2 pr-10 pl-3 text-left bg-white rounded-lg shadow-md cursor-default 
            focus:outline-none focus-visible:border-indigo-500 focus-visible:ring-2 focus-visible:ring-white 
            focus-visible:ring-opacity-75 focus-visible:ring-offset-2 focus-visible:ring-offset-blue-500 
            focus:shadow-none"
        >

    </div>
</template>

<script setup lang="ts">


  defineProps(['modelValue', 'label'])
  defineEmits(['update:modelValue'])


</script>

