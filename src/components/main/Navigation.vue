<template>
    <div class="px-16 py-2 flex justify-center w-full bg-black opacity-90">
        <div class="w-1/4 flex justify-start">
        <img src="../../assets/logo.png" class="w-24 h-14" />
        </div>
        <ul class="w-3/4 flex justify-center py-2 list-none gap-4">
        <li v-for="navL in navLinks" :key="navL.id">
            <router-link :to="navL.link" class="text-sm font-bold tracking-wide text-white">
                {{ navL.name }}
            </router-link>
        </li>
        </ul>
    </div>
</template>

<script>
export default {
    data(){
        return{
            navLinks:[
                {
                    id:1,
                    name:'Home',
                    link:'/',
                },
                {
                    id:2,
                    name:'About',
                    link:'/about',
                },
                {
                    id:3,
                    name:'Services',
                    link:'/services',
                },
                {
                    id:4,
                    name:'Blog',
                    link:'/blogs',
                },
                {
                    id:5,
                    name:'Contact',
                    link:'/contact',
                }
            ]
        }
    }
}
</script>