<template>
    <li>
        <div class=" flex hover:bg-gray-200 hover:text-gray-800 rounded ">
            <div v-if="icone != undefined" class="flex items-center pl-2 pointer-events-none" >
                <div :class="'w-5 h-5 stroke-current '+[icone]"/>
            </div>
            <NuxtLink
                :to="item"
                class=" flex w-full px-4 py-2 text-xs rounded hover:bg-gray-200 hover:text-gray-800 focus:outline-none  focus:text-gray-800"
                >{{ item }}
                <div class="group/edit invisible  group-hover/item:visible">
                    <span class="group-hover/edit:text-gray-100"> Call</span>
                </div>
            </NuxtLink>
        </div>
    </li>
</template>

<script setup lang="ts">

    import { defineProps } from 'vue';

    const props = defineProps({
        icone: {
            type: String,
            required: false,
        },
        item: {
            type: String,
            required: true,
            default: 'PPR_GQ_01'
        }
    });


</script>