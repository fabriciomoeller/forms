<template>
  <div class="flex flex-col">
        
        <fieldset class=" border-b border-2  rounded-lg shadow-md cursor-default p-2">
          <legend  class="truncate">{{ label }}</legend>
          <div class="flex items-center space-x-4">
            <radio-due  
              v-model="model"  
              :value="value"  
              :name="label"
            />
          </div>
        </fieldset>

    </div>
</template>

<script setup lang="ts">

  import { defineProps,computed, defineEmits } from "vue";
  import radioDue from "./radioDue.vue";

  const props = defineProps({
        label: { type: String }, 
        modelValue: { type: String }, // Envia/Retorna o valor do checkbox
        value: { type: [Array] },  // Envia o valor do checkbox
    });
    const emit = defineEmits(["update:modelValue"]);
    const model = computed({
    get() {
        return props.modelValue;
    },
    set(value) {
        emit("update:modelValue", value);
    },
    });


</script>

