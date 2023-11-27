<template>
    <div class=" hidden md:block px-6 pt-4">
        <div class="relative text-gray-400">
            <div  class="absolute inset-y-0 left-0 flex items-center pl-2 pointer-events-none "
            >
            <div class="w-4 h-4 stroke-current i-carbon:search " />
            
            </div>
            <!-- No input foi usado Modo Atributo do UNOCSS para agrupar classes por atributo -->
            <input 
                type="text"
                class="w-full 
                    rounded 
                    pl-8 pr-4 py-2.5 
                    text-sm 
                    font-light
                    dark:bg-gray-900"
                focus="outline-none ring-2"
                border="1 yellow-500 hover:gray-600 dark:red-600 hover:dark:green-400"
                placeholder="pesquisar"
            />
        </div>
    </div>
</template>