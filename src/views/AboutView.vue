<template>
  <div class="home -mt-10">
    <HeaderImage title="About"  :backgroundImage="backgroundImage"/>
    <!-- intro part -->
    <div class="flex px-5 section">
      <div class="intro-block">
        <div class="intro-block-left">
          <div class="">
            <img
              src="../assets/images/about-2.jpg"
              class="intro-block-left-image"
            />
          </div>
          <div class="">
            <img
              src="../assets/images/about1.jpg"
              class="intro-block-left-image2"
            />
          </div>
        </div>
      </div>
      <IntroBlock :title="title" :subtitle="subtitle" :introText="introText" :introduce="introduce"  />
    </div>
    <!-- intro part end -->

    <!-- product list -->
    <div class="section relative">
      <span class="section-title user-select-none"> REASON TO CHOOSE US </span>
      <p class="section-subtitle user-select-none">
        We provide truly prominent IT solutions.
      </p>
      <SolutionBlock :ourSolution="ourSolution"  @solutionView="solutionView"/>
      <div
        v-if="show"
        class="absolute w-full h-auto left-0 top-40 flex justify-center "
      >
        <div
          class="w-1/2 h-auto py-5 px-5 bg-white rounded-lg block shadow-xl shadow-gray-400"
        >
          <div class="product-icon-block py-3">
            <img :src="solution.image" />
          </div>
          <p class="product-type">
            {{ solution.title }}
          </p>
          <p class="product-details leading-7">
            {{ solution.details }}
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
    </div>
    <!-- product list end -->

    <div class="section background-image">
      <span class="section-title text-white user-select-none">
        OUR EXPERT TEAM
      </span>
      <p class="section-subtitle text-white user-select-none">
        We have world expert team
      </p>
      <div class="team-expart-block">
        <div
          v-for="ourT in ourTeams"
          :key="ourT.id"
          class="relative w-full h-auto group"
        >
          <img :src="ourT.image" class="team-expart-block-image" />
          <div
            class="absolute top-2/4 left-0 right-0 bg-opacity-50 text-white p-2 group-hover:bg-opacity-100"
          >
            <div
              class="team-expart-block-details"
            >
              <p class="team-expart-block-details-name">
                {{ ourT.name }}
              </p>
              <p class="team-expart-block-details-designation">
                {{ ourT.designation }}
              </p>
            </div>

            <ul class="team-expart-block-details-ul">
              <li v-for="social in ourT.social" :key="social">
                <i
                  :class="social"
                  class="team-expart-block-details-ul-icon"
                ></i>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>

    <!-- testimonial part -->
    <div class="px-0 section">
      <HeadingTitle title="TESTIMONIAL" subtitle="20k+ satisfied clients worldwide" />
      <div class="testemonial-swiper">
        <SwiperView />
      </div>
      <div class="testemonial-partner-swiper">
        <PartnerSwiper />
      </div>
    </div>
    <!-- testimonial part end -->
  </div>
</template>

<script>
import SwiperView from "@/components/swiper/SwiperView.vue";
import PartnerSwiper from "@/components/swiper/PartnerSwiper.vue";
import HeadingTitle from "@/components/main/HeadingTitle.vue";
import HeaderImage from "@/components/main/HeaderImage.vue";
import IntroBlock from "@/components/card/IntroBlock.vue";
import SolutionBlock from "@/components/card/SolutionBlock.vue";
import {ourSolution,ourTeams,introduce,socialLinks} from '../jsonStore/store';

export default {
  data() {
    return {
      ourSolution:ourSolution,
      ourTeams:ourTeams,
      introduce:introduce,
      socialLinks:socialLinks,
      show:false,
      title:"WHO WE ARE",
      subtitle:"We run all kinds of software services that vow your success",
      introText:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos modi tenetur, amet eveniet a placeat voluptatum natus doloremque cumque cupiditate adipisci officia alias, illo voluptate unde veniam maxime accusantium. Nam.",
      backgroundImage:'home-header',

      solution:{},

    };
  },
  components: {
    SwiperView,
    PartnerSwiper,
    HeadingTitle,
    HeaderImage,
    IntroBlock,
    SolutionBlock
  },

  mounted(){
        window.scrollTo(0,0)
    },

    methods:{
      solutionView(data) {
      this.solution = data;
      this.show = true;
    },
      closeView(){
        this.show = false;
      }
    }

};
</script>

<style scoped>
.home-header {
  background-image: url("../assets/images/2.jpg");
  background-size: cover;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}

.background-image {
  background-image: url("../assets/images/3.jpg");
  background-size: cover;
  height: 80vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>
