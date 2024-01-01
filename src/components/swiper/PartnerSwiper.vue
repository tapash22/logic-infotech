<template>
    <div>
      <carousel :autoplay="true" :show-pagination="false" :per-page="4"  class="bg-white">
        <slide v-for="i in partners" :key="i.id" class="py-3">
          <div class="w-full h-auto flex justify-center items-center bg-white px-2">
            <img :src="i.image" class="ring-2 ring-indigo-900 rounded-lg w-44" />
          </div>
        </slide>
      </carousel>
    </div>
  </template>
  
  <script>
  import { Carousel, Slide } from "vue-carousel";
  
  export default {
    data() {
      return {
        partners: [
          {
            id: 1,
            name: "partner",
            image: require("../../assets/partner/du.png"),
          },
          {
            id: 2,
            name: "partner",
            image: require("../../assets/partner/baf.png"),
          },
          {
            id: 3,
            name: "partner",
            image: require("../../assets/partner/rab.png"),
          },
          {
            id: 4,
            name: "partner",
            image: require("../../assets/partner/bkmea.jpg"),
          },
          {
            id: 5,
            name: "partner",
            image: require("../../assets/partner/bd.jpg"),
          },
        ],
      };
    },
    components: {
      Carousel,
      Slide,
    },
  };
  </script>
  
  <style scoped>
  /* Your component styles here */
  </style>
  