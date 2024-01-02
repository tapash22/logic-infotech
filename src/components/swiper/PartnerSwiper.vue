<template>
  <div>
    <carousel
      :autoplay="true"
      :show-pagination="true"
      :per-page="6"
      :loop="true"
      :interval="100"
      :pagination-class="'custom-pagination'"
      :pagination-active-class="'custom-pagination-active'"
    >
      <slide v-for="partner in partners" :key="partner.id">
        <div class="py-3">
          <div
            class="w-full h-auto flex justify-center items-center bg-white px-2"
          >
            <img
              :src="partner.image"
              class="ring-2 ring-indigo-900 rounded-lg w-44"
            />
          </div>
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
          image: require("../../assets/partner/bkmea.jpg"),
        },
        {
          id: 6,
          name: "partner",
          image: require("../../assets/partner/rab.png"),
        },
        {
          id: 7,
          name: "partner",
          image: require("../../assets/partner/bkmea.jpg"),
        },
        {
          id: 8,
          name: "partner",
          image: require("../../assets/partner/bkmea.jpg"),
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
  
<style >
.VueCarousel-dot {
  visibility: hidden;
}
</style>
  