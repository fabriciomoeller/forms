<template>
    <li>
        <div class="relative flex flex-col text-gray-500">
            <div class=" flex hover:bg-gray-200 hover:text-gray-800 rounded ">
            
                <div v-if="icone != undefined" class="flex items-center pl-2 pointer-events-none" >
                    <div :class="'w-5 h-5 stroke-current '+[icone]"/>
                </div>
                <a
                v-on:click="isOpen = !isOpen" 
                href="#"
                class="flex w-full px-2 py-2 pl-2 text-sm focus:outline-none  focus:text-gray-800"
                > {{ itemPai }}
                <div class=" absolute right-1 w-4 h-4 stroke-current i-ic:baseline-keyboard-arrow-down"/>
                </a>
            </div>

            <div class="pt-2 pl-4">
                <ul class="border-l pl-2 border-gray-700">
                <li-item 
                    v-for="item in children"
                    :item="item.codigo"
                    :key="item.codigo" 
                    :title="item.descricao"
                    :class=" isOpen ? 'block' : 'hidden'"
                    />
                    
                
                </ul>
            </div>
        </div>
    </li>
</template>

<script setup lang="ts">

    import { ref } from 'vue';
    import { defineProps } from 'vue';
    import liItem from './liItem.vue';

    const isOpen = ref(false);
    const props = defineProps({
        icone: {
            type: String,
            required: false
        },
        itemPai: {
            type: String,
            required: true,
            default: 'RECEBIMENTO DE MATÉRIA PRIMA SECUNDÁRIA'
        },
        children: {
            type: Array,
            required: true,
            default: [{ 'codigo':'PPR_GQ_01', 'descricao':'CONTROLE DE RECEBIMENTO DE EMBALAGENS PRIMÁRIAS - BIG BAGS'}],
        }
    });



</script>