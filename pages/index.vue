<script setup>
    import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
    import TabsToday from '@/components/Tabs/Today.vue'
    const loading = ref(false)
    const list =[
        {
            title: 'Today',
            component: TabsToday
        },
        {
            title: 'This Week',
            des: 'Hello Todalyasdfwer'
        },
        {
            title: 'This Month',
            des: 'Hello Todaly2354'
        },
        {
            title: 'This Year',
            des: 'Hello Todalyasdf'
        }
    ]
</script>
<template>
    <div class="grid gap-8 h-screen">
        <header class="flex items-starts justify-between">
            <div class="grow">
                <p class=" text-neutral-400">Hi, Welcome back Asad!</p>
                <h1>Dashboard</h1>
            </div>
            <div class="w-[120px] h-12 bg-neutral-200"></div>

        </header>
        <main>
            <Tabs default-value="account" class="w-[400px">
                <TabsList class="">
                  <TabsTrigger v-for="item, index in list" :key="index" :value="item.title">
                    {{item.title}}
                  </TabsTrigger>                  
                </TabsList>
                <TabsContent v-for="item, index in list" :key="index" :value="item.title">
                    <component v-if="item.component" :is="item.component" />
                   <p v-else> {{ item.des }}</p>
                </TabsContent>               
              </Tabs>
        </main>
        <footer>
            <p>will have 3 card</p>
        </footer>
    </div>
</template>