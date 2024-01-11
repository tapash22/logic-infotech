<template>
  <div class="home -mt-10">
    <div class="home-header home-banner">
      <p class="page-heading">Services</p>
    </div>
    <div class="section relative">
      <ServiceBlock :ourServices="ourServices" @serviceView="serviceView" />
      <div
        v-if="show"
        class="absolute w-full h-auto left-0 top-40 flex justify-center "
      >
        <div
          class="w-1/2 h-auto py-5 px-5 bg-white rounded-lg block shadow-xl shadow-gray-400"
        >
          <div class="product-icon-block py-3">
            <img :src="service.image" />
          </div>
          <p class="product-type">
            {{ service.title }}
          </p>
          <p class="product-details leading-7">
            {{ service.details }}
          </p>
          <p class="text-sm font-medium tracking-wide text-justify">
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Optio,
            quam autem facilis sunt mollitia accusamus facere laboriosam quos.
            Aperiam voluptate maxime minus, et aut magnam expedita qui. Tempore,
            cupiditate atque!
          </p>
        </div>
        <div class="absolute" >
          <i class="fa fa-times font-normal text-2xl text-red-500" @click="closeView"></i>
        </div>
      </div>
    </div>

    <!-- contact information -->
    <div class="section px-12">
      <div class="service-cover flex justify-start px-5 rounded-lg">
        <div class="flex justify-between items-center px-5 py-5">
          <div class="w-1/2 flex justify-start">
            <h1
              class="font-bold tracking-wide flex justify-start px-2 py-3 text-4xl border-l-4 border-white text-white mr-36 mb-5 user-select-none"
            >
              To make requests for further information, contact us
            </h1>
          </div>
          <div class="block w-1/2">
            <div class="flex justify-center items-center">
              <img src="../assets/services/icon.png" />
            </div>
            <span
              class="text-sm font-normal py-2 flex justify-center text-white"
            >
              Call Us For Any inquiry
            </span>
            <p class="text-3xl font-bold py-2 flex justify-center text-white">
              +8801600000000
            </p>
          </div>
        </div>
      </div>
    </div>
    <!-- contact information end -->

    <!-- testimonial part -->
    <div class="section px-0">
      <HeadingTitle
        title="TESTIMONIAL"
        subtitle="20k+ satisfied clients worldwide"
      />
      <div class="testemonial-swiper">
        <SwiperView />
      </div>
      <div class="testemonial-partner-swiper">
        <PartnerSwiper />
      </div>
    </div>
    <!-- testimonial part end -->

    <!-- modal view -->

    <!-- modal view end -->
  </div>
</template>

<script>
import SwiperView from "@/components/swiper/SwiperView.vue";
import PartnerSwiper from "@/components/swiper/PartnerSwiper.vue";
import ServiceBlock from "@/components/card/ServiceBlock.vue";
import HeadingTitle from "@/components/main/HeadingTitle";

export default {
  data() {
    return {
      show: false,
      service: {},
      ourServices: [
        {
          id: 1,
          title: "IT Consultancy",
          image: require("../assets/icon-image/1.png"),
          details:
            "Accelerate innovation with world-class tech teams We’ll match you to an entire.",
        },
        {
          id: 2,
          title: "Data Science",
          image: require("../assets/icon-image/2.png"),
          details:
            "Accelerate innovation with world-class tech teams We’ll match you to an entire.",
        },
        {
          id: 3,
          title: "IT Security",
          image: require("../assets/icon-image/3.png"),
          details:
            "Accelerate innovation with world-class tech teams We’ll match you to an entire.",
        },
        {
          id: 4,
          title: "blockchain System",
          image: require("../assets/icon-image/4.png"),
          details:
            "Accelerate innovation with world-class tech teams We’ll match you to an entire.",
        },
        {
          id: 5,
          title: "IT Infrustructure",
          image: require("../assets/icon-image/5.png"),
          details:
            "Accelerate innovation with world-class tech teams We’ll match you to an entire.",
        },
        {
          id: 6,
          title: "Data Managment",
          image: require("../assets/icon-image/6.png"),
          details:
            "Accelerate innovation with world-class tech teams We’ll match you to an entire.",
        },
        {
          id: 7,
          title: "IT Managment",
          image: require("../assets/icon-image/7.png"),
          details:
            "Accelerate innovation with world-class tech teams We’ll match you to an entire.",
        },
        {
          id: 8,
          title: "Data securet",
          image: require("../assets/icon-image/8.png"),
          details:
            "Accelerate innovation with world-class tech teams We’ll match you to an entire.",
        },
      ],
    };
  },

  methods: {
    serviceView(data) {
      this.service = data;
      this.show = true;
    },

    closeView(){
      this.show = false;
    }
  },

  components: {
    SwiperView,
    PartnerSwiper,
    ServiceBlock,
    HeadingTitle,
  },

  mounted() {
    window.scrollTo(0, 0);
  },
};
</script>

<style scoped>
.home-header {
  /* background-image: url("../assets/images/hero2-bg.jpg"); */
  background-image: url("../assets/images/about.jpg");
  /* background-image: url("../assets/images/2.jpg"); */
  /* background-image: url("../assets/images/3.jpg"); */
  background-size: cover;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}

.service-cover {
  background-image: url("../assets/services/background.jpg");
  /* background-position: center; */
  background-size: cover;
  object-fit: cover;
}
</style>