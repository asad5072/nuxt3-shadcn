<script setup>
const open = ref(true)
</script>
<template>
    <div class="">
        <div class=" flex items-center justify-between gap-4 w-full h-full z-50 p-4 lg:hidden ">
            <Logo />
            <Icon name="ic:baseline-sort" class="z-950 absolute top-4 right-4 cursor-pointer" size="30" @click="open = true" />
            
            <div v-if="open" class="fixed top-0 left-0 z-950 w-full h-screen bg-white">
                <Icon name="ic:baseline-close" class="absolute top-4 right-4 cursor-pointer z-50" size="30" @click="open = false" />
                <SidebarMenu />
            </div>

        </div>
        <div class=" hidden lg:flex flex-col w-[250px] h-screen border-r justify-between">
            <SidebarMenu />
            <div>UserItem</div>
        </div>

    </div>
</template>