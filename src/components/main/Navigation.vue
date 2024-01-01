<template>
    <div class="px-16 py-0 flex justify-center w-full  border-b-2 border-gray-300 shadow-xl navigation">
        <div class="w-1/4 flex justify-start py-2">
        <img src="../../assets/logo/info.png" class="w-28 h-16" />
        </div>
        <ul class="w-3/4 flex justify-end items-center list-none gap-4 ">
        <li v-for="navL in navLinks" :key="navL.id">
            <router-link :to="navL.link" class="text-lg font-bold tracking-wide text-black">
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

<style scoped>
.navigation{
    background: #ebe5e5c6;
}
</style>