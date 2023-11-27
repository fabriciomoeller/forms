<template>
    
        <div v-for="item in value" :key="item" class="flex space-x-2">
            <input type="radio" 
                v-model="model" 
                :value="item"
                :name="name" />
            <label :for="item" class="">{{ item }}</label>

        </div>
    
</template>

<script setup lang="ts">
    
    import { defineProps,computed, defineEmits } from "vue";
    
    // https://dev.to/maxwelladapoe/creating-a-custom-checkbox-component-in-vue-3-a-better-approach-2jjd

    const props = defineProps({
        name: { type: String },
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

<style >
  input[type="radio"] + label span {
      transition: background .2s,
        transform .2s;
  }

  input[type="radio"] + label span:hover,
  input[type="radio"] + label:hover span{
    transform: scale(1.2);
  } 

  input[type="radio"]:checked + label span {
    background-color: #116cb8;
    box-shadow: 0px 0px 0px 2px white inset;
  }

  input[type="radio"]:checked + label{
    color: #116cb8;
  }
</style>