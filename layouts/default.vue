
<!-- import { Sidebar } from 'lucide-vue-next'; -->
<template>
    <div class="grid items-start lg:flex">
        <div>
            <Sidebar />
        </div>
        <div class="w-full p-4">
            <slot />
        </div>
    </div>
  </template>