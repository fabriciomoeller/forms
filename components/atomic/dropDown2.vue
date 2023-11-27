<template>
    <div class="flex flex-col">
    <Listbox 
        :modelValue="modelValue"
        @update:modelValue="value => emit('update:modelValue', value)"
        by="id"  >
      <ListboxButton class="flex h-8 px-3 py-2 bg-white w-full border-b border-gray-500 ">{{  modelValue.name }}</ListboxButton>
      <ListboxOptions class="bg-white text-base z-50 list-none p-2 rounded shadow my-4">
        <ListboxOption
        v-for="department in departments"
        :key="department.id"
        :value="department"
        class="ui-active:bg-blue-500 ui-active:text-white ui-not-active:bg-white ui-not-active:text-black"
      >
        {{ department.name }}
      </ListboxOption>

          
      
      </ListboxOptions>
    </Listbox>
    </div>
  </template>
  
  <script setup>
    import { ref } from 'vue'
    import {
      Listbox,
      ListboxButton,
      ListboxOptions,
      ListboxOption,
    } from '@headlessui/vue'
    
  
    const props = defineProps({ modelValue: Object })
  const emit = defineEmits(['update:modelValue'])

  const departments = [
    { id: 1, name: 'Marketing', contact: 'Durward Reynolds' },
    { id: 2, name: 'HR', contact: 'Kenton Towne' },
    { id: 3, name: 'Sales', contact: 'Therese Wunsch' },
    { id: 4, name: 'Finance', contact: 'Benedict Kessler' },
    { id: 5, name: 'Customer service', contact: 'Katelyn Rohan' },
  ]
  </script>