<template>
    <div
        class="absolute w-full h-auto left-0 top-40 flex justify-center "
      >
        <div
          class="w-1/2 h-auto py-5 px-5 bg-white rounded-lg block shadow-xl shadow-gray-400"
        >
          <div class="product-icon-block py-3">
            <img :src="popupview.image" />
          </div>
          <p class="product-type">
            {{ popupview.title }}
          </p>
          <p class="product-details leading-7">
            {{ popupview.details }}
          </p>
          <p class="text-sm font-medium tracking-wide text-justify">
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Optio,
            quam autem facilis sunt mollitia accusamus facere laboriosam quos.
            Aperiam voluptate maxime minus, et aut magnam expedita qui. Tempore,
            cupiditate atque!
          </p>
          <router-link to="/contact" class=" flex justify-start gap-2 py-3 cursor-pointer">
            <span class="text-lg font-bold text-indigo-950 tracking-wide underline underline-offset-4">Contact with us</span> 
          </router-link>
          <div class=" block">
            <ul class="list-none flex gap-2">
              <li v-for="sl in socialLinks" :key="sl.id" class="w-10 h-10 rounded-full bg-indigo-950 opacity-80 hover:opacity-100 transition-all delay-100 flex justify-center items-center">
                <a :href="sl.link" class="no-underline">
                  <i :class="sl.icon" class="text-2xl font-sm text-white"></i>
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div class=" flex justify-center items-center -mt-2 -ml-5 w-10 h-10 rounded-full bg-white ring-2 ring-gray-400 cursor-pointer" >
          <i class="fa fa-times fa-1x font-normal text-2xl text-gray-500" @click="closeView"></i>
        </div>
      </div>
</template>

<script>
export default {
    props:["popupview","socialLinks"],

    methods:{
        closeView(){
            this.$emit("closeView")
        }
    }
}
</script>