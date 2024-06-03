<script setup>
    import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
    import TabsToday from '@/components/Tabs/Today.vue'
    const loading = ref(false)
    let categories = ref({
        'today' :[],
        'week': [],
        'month': [],
        'year': []
    })
    let currentCategory = ref([
            'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep',
            'Oct', 'Nov', 'Dec'
        ])
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
    const options = computed(() => (
    {
    chart: {
        type: 'line'
    },
    title: {
        text: ''
    },
    // subtitle: {
    //     text: 'Source: ' +
    //         '<a href="https://en.wikipedia.org/wiki/List_of_cities_by_average_temperature" ' +
    //         'target="_blank">Wikipedia.com</a>'
    // },
    xAxis: {
        gridLineColor: 'transparent',
        categories: currentCategory
    },
    yAxis: {
        gridLineColor: 'transparent',
        title: {
            // text: 'Temperature (°C)'
        }
    },
    plotOptions: {
        line: {
            marker: {
                enabled: false
            },
            dataLabels: {
                enabled: true
            },
            enableMouseTracking: true
        }
    },
    series: [{
        name: 'Reggane',
        data: [
            16.0, 18.2, 23.1, 27.9, 32.2, 36.4, 39.8, 38.4, 35.5, 29.2,
            22.0, 17.8
        ]
    }, {
        name: 'Tallinn',
        data: [
            -2.9, -3.6, -0.6, 4.8, 10.2, 14.5, 17.6, 16.5, 12.0, 6.5,
            2.0, -0.9
        ]
    }]
}
    ))
    
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
            <Tabs default-value="Today" class="w-[400px">
                <TabsList class="">
                  <TabsTrigger v-for="item, index in list" :key="index" :value="item.title">
                    {{item.title}}
                  </TabsTrigger>                  
                </TabsList>
                <TabsContent v-for="item, index in list" :key="index" :value="item.title">
                    <!-- <component v-if="item.component" :is="item.component" />
                   <p v-else> {{ item.des }}</p> -->
                   <highchart :options="options" />
                </TabsContent>               
              </Tabs>
        </main>
        <footer>
            <p>will have 3 card</p>
        </footer>
    </div>
</template>