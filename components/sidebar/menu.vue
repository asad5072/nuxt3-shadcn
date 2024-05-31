<script setup>
    const items = ref([
        {
            title: 'Overview',
            path : '/',
            icon: 'ic:outline-dashboard'
        },{
            title: 'Transactions',
            path: '/transaction'
        },{
            title : 'Accounts',
            path: '/account'
        },{
            title: 'Settings',
            path: '/setting'
        }
    ])
</script>
<template>
    <header class="flex items-center gap-2 p-4 hover:scale[101%] transition cursor-pointer">
        <Logo />
        <div class="font-bold">Nuxt Finance</div>
    </header>
    <div class="grow px-4">
        <div class="grid gap-4">
            <NuxtLink :href="item.path" v-for="(item, index) in items" :key="index" class="flex items-center gap-2 px-2 py-1 transition rounded cursor-pointer hover:bg-neutral-100">
                <!-- <Icon size="20" :name="item.icon" color="black" /> -->
                <span>{{ item.title }}</span>
            </NuxtLink>
        </div>
    </div>
</template>