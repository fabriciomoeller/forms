<template>
    
    <!-- This is an example component -->
    <div class="flex justify-center">
        <label for="toogleButton" class="flex items-center cursor-pointer">
        <div class="text-sm font-medium text-gray-700 px-2">{{ label }}</div>
    <!-- toggle -->
    <div class="relative">
        <input 
            id="toogleButton" 
            type="checkbox" 
            v-model="model" 
            :value="value" 
            class="hidden" />
        <!-- path -->
        <div
        class="toggle-path bg-gray-200 w-9 h-5 rounded-full shadow-inner"
        ></div>
        <!-- crcle -->
        <div
        class="toggle-circle absolute w-3.5 h-3.5 bg-white rounded-full shadow inset-y-0 left-0"
        ></div>
    </div>
    </label>

    </div>


</template>

<script setup lang="ts"> 

    import { defineEmits, computed } from 'vue';

    const props = defineProps({
        modelValue: { type: [Array, Boolean] }, // Envia/Retorna o valor do checkbox
        value: { type: [Boolean, Object] },  // Envia o valor do checkbox
        label: { type: String }, // O que vai ser mostrado ao lado do checkbox
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

<style>

.toggle-path {
   transition: background 0.3s ease-in-out;
}
.toggle-circle {
   top: 0.2rem;
   left: 0.25rem;
   transition: all 0.3s ease-in-out;
}
input:checked ~ .toggle-circle {
   transform: translateX(100%);
}
input:checked ~ .toggle-path {
   background-color:#76e2d7;
}
</style>