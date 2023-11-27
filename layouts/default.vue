<template>
  <main class="block"> 
    <div class="fixed w-full bg-gray-100 dark:bg-dark-800">
      <top-bar class=" h-16 border-b-1 border-gray-300  dark:border-gray-600"/>
      <div class=" block h-full w-full " >
          <side-bar class=" bg-gray-100 dark:bg-dark-800 
            fixed h-screen overflow-y-auto py-6 
            pb-12 w-screen md:w-48 z-20 
            border-r-1 border-gray-300  dark:border-gray-600
            cursor-pointer "/>
          <div class="pl-10 pt-8 pr-10 pb-12 px-4 overflow-y-auto md:pl-60  bg-gray-100 dark:bg-dark-800">
            <slot /> 
          </div>
          
      </div>
    </div>
  </main>
</template>

