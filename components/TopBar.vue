<template>
    <div class="p-0.5">
        <button @click="$event => setThemeMode($colorMode.preference === 'light' ? 'dark' : 'light')"
                class="w-20 h-10 flex items-center justify-center border-gray-400 border-1 rounded-md
                    p-2 m-2 right-1 top-1 absolute
                    focus-visible:n-focus-base n-transition 
                    hover:border-green-500 hover:text-green-500
                    n-disabled:n-disabled
                    dark:text-white">
                <div class=" w-10 h-8 i-carbon-sun dark:i-carbon-moon"></div>
                {{ $colorMode.preference === 'light' ? 'light' : 'dark' }}
            </button>
        </div>
</template>
<script setup lang="ts">
type theme = 'light' | 'dark';

const setThemeMode = (newTheme: theme) => {
  useColorMode().preference = newTheme;
};
</script>