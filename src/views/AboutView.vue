<template>
  <div class="home -mt-10">
    <div class="home-header home-banner"></div>
    <!-- intro part -->
    <div class="flex px-5 section">
      <div class="w-1/2 h-auto flex justify-center">
        <div class="w-full h-auto px-2 flex justify-center gap-3 rounded-xl">
          <div class="">
            <img
              src="../assets/images/about-2.jpg"
              class="object-cover w-full h-full rounded-lg"
            />
          </div>
          <div class="">
            <img
              src="../assets/images/about1.jpg"
              class="object-cover w-full h-auto rounded-lg -mt-10"
            />
          </div>
        </div>
      </div>
      <div class="w-1/2 h-auto pr-32 block pl-9">
        <span class="text-sm font-normal tracking-wide flex justify-start">
          WHO WE ARE
        </span>
        <p
          class="text-5xl font-bold tracking-normal py-3 flex justify-center leading-none"
        >
          We run all kinds of software services that vow your success
        </p>
        <p
          class="text-sm font-medium tracking-normal text-justify break-words leading-7 py-2"
        >
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos modi
          tenetur, amet eveniet a placeat voluptatum natus doloremque cumque
          cupiditate adipisci officia alias, illo voluptate unde veniam maxime
          accusantium. Nam.
        </p>

        <!-- last part -->
        <div class="w-full my-3 px-3 flex justify-between gap-5">
          <div
            class="block bg-gray-200 rounded-lg py-3 px-3"
            v-for="intro in introduce"
            :key="intro.id"
          >
            <div class="flex justify-center">
              <!-- <i
                class="fa fa-arrow-right text-sm w-6 h-6 mx-1 bg-indigo-950 rounded-full text-white flex justify-center items-center"
                aria-hidden="true"
              ></i> -->
              <span class="tracking-wide text-black text-lg font-bold">
                {{ intro.name }}
              </span>
            </div>
            <p
              class="text-sm font-normal text-indigo-950 flex justify-center text-justify py-2"
            >
              {{ intro.details }}
            </p>
          </div>
        </div>
        <!-- last part end -->
      </div>
    </div>
    <!-- intro part end -->

    <!-- product list -->
    <div class="section">
      <span class="section-title user-select-none"> REASON TO CHOOSE US </span>
      <p class="section-subtitle user-select-none">
        We provide truly prominent IT solutions.
      </p>
      <div class="grid grid-cols-4 gap-3 py-2 px-5">
        <div v-for="i in 8" :key="i" class="bg-gray-400 py-3 rounded-lg px-3">
          <div class="product-icon-block">
            <i class="icon-card product-icon fa fa-code" > </i>
          </div>
          <p class="product-type">
            {{ i }}
          </p>
          <p class="product-details">
           Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis quidem nesciunt, saepe laborum, quia ab quam nostrum autem, odio voluptatibus aspernatur itaque. Architecto eligendi nisi minus deserunt quasi, tempore dolorum.
          </p>
        </div>
      </div>
    </div>
    <!-- product list end -->

    <div class=" section">
      <span class="section-title user-select-none"> OUR EXPERT TEAM </span>
      <p class="section-subtitle user-select-none">
        We have world expert team
      </p>
      </div>

    <!-- testimonial part -->
    <div class="bg-gray-300 section">
      <span class="section-title user-select-none"> TESTIMONIAL </span>
      <p class="section-subtitle user-select-none">
        20k+ satisfied clients worldwide
      </p>
      <div class="px-12 py-3">
        <SwiperView />
      </div>
      <div class="px-8 py-3">
        <PartnerSwiper />
      </div>
    </div>
    <!-- testimonial part end -->

    <!-- contact block -->

    <!-- contact block end -->
  </div>
</template>

<script>
import SwiperView from "@/components/swiper/SwiperView.vue";
import PartnerSwiper from "@/components/swiper/PartnerSwiper.vue";

export default {
  data() {
    return {
      introduce: [
        {
          id: 1,
          name: "Expert Team",
          details:
            "Accelerate innovation with world-class tech teams. We help businesses elevate their value.",
        },
        {
          id: 2,
          name: "Custom Code",
          details:
            "Accelerate innovation with world-class tech teams. We help businesses elevate their value.",
        },
      ],
    };
  },
  components: {
    SwiperView,
    PartnerSwiper,
  },
};
</script>

<style scoped>
.home-header {
  /* background-image: url("../assets/images/hero2-bg.jpg"); */
  background-image: url("../assets/images/2.jpg");
  /* background-image: url("../assets/images/2.jpg"); */
  /* background-image: url("../assets/images/3.jpg"); */
  background-size: cover;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>
