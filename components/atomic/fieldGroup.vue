<script setup lang="ts">

import fieldCheckBox from '../atomic/checkBox.vue';
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
    <fieldset class="grid lg:grid-cols-2 gp-4 p-4 border rounded-md">
        <legend class="ml-2"> {{ legend }} </legend>
        <fieldCheckBox
            v-for="item in value" :key="item.value"
            :label="item.label"
            :fieldId="item.value"
            :checked="item.selected"
            class="space-y-2 "
        />
    </fieldset>
        
    
</template>