<script setup lang="ts">

import fieldRadio from '../atomic/fieldRadio.vue';
import fieldString from '../atomic/fieldString.vue';

const props = defineProps({
    modelValue: {
        type: Array,
        required: true,
    },
    fieldId: {
        type: String,
        required: true,
    },
    value: {
        type: Object,
    },
    legend: {
        type: String,
        required: true,
    },
});

const checked = ref(false);

</script>
<template>
    <fieldset class="grid lg:grid-cols-2  p-4 border rounded-md ">
        <legend class="ml-2"> {{ legend }} </legend>
        <field-radio 
            v-for="item in value" :key="item.value" 
            :label="item.label" 
            :modelValue="item.radio.selected" 
            :value="item.radio"
            class="space-x-2" />
    

    </fieldset>
        
    
</template>