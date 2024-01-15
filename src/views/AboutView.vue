<template>
  <div class="home -mt-10">
    <HeaderImage title="About" :backgroundImage="backgroundImage" />
    <!-- intro part -->
    <div class="flex px-5 section">
      <div class="intro-block">
        <div class="intro-block-left">
          <div class="">
            <img :src="aboutImage1" class="intro-block-left-image" />
          </div>
          <div class="">
            <img :src="aboutImage2" class="intro-block-left-image2" />
          </div>
        </div>
      </div>
      <!-- <IntroBlockImage :aboutImage1="aboutImage1" :aboutImage2="aboutImage2" /> -->
      <IntroBlock
        :title="title"
        :subtitle="subtitle"
        :introText="introText"
        :introduce="introduce"
      />
    </div>
    <!-- intro part end -->

    <!-- product list -->
    <div class="section relative">
      <HeadingTitle
        title="REASON TO CHOOSE US"
        subtitle="We provide truly prominent IT solutions."
      />
      <SolutionBlock :ourSolution="ourSolution" @solutionView="solutionView" />

      <PopupModal
        v-if="show"
        :popupview="solution"
        :socialLinks="socialLinks"
        @closeView="closeView"
      />
    </div>
    <!-- product list end -->

    <div class="section background-image">
      <HeadingTitle
        title="OUR EXPERT TEAM"
        subtitle="We have world expert team"
        :expartStyle="{ color: 'white' }"
      />
      <TeamExpartBlock :ourTeams="ourTeams" />
    </div>

    <!-- testimonial part -->
    <div class="px-0 section">
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
  </div>
</template>

<script>
import SwiperView from "@/components/swiper/SwiperView.vue";
import PartnerSwiper from "@/components/swiper/PartnerSwiper.vue";
import HeadingTitle from "@/components/main/HeadingTitle.vue";
import HeaderImage from "@/components/main/HeaderImage.vue";
import IntroBlock from "@/components/card/IntroBlock.vue";
import SolutionBlock from "@/components/card/SolutionBlock.vue";
import {
  ourSolution,
  ourTeams,
  introduce,
  socialLinks,
} from "../jsonStore/store";
import PopupModal from "@/components/modal/PopupModal";
import TeamExpartBlock from "@/components/card/TeamExpartBlock.vue";
// import IntroBlockImage from "@/components/card/IntroBlockImage.vue";
import image1 from "@/assets/images/about2.jpg";
import image2 from "@/assets/images/about1.jpg";

export default {
  data() {
    return {
      textColor: 'red',
      ourSolution: ourSolution,
      ourTeams: ourTeams,
      introduce: introduce,
      socialLinks: socialLinks,
      show: false,
      title: "WHO WE ARE",
      subtitle: "We run all kinds of software services that vow your success",
      introText:
        "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos modi tenetur, amet eveniet a placeat voluptatum natus doloremque cumque cupiditate adipisci officia alias, illo voluptate unde veniam maxime accusantium. Nam.",
      backgroundImage: "home-header",
      solution: {},
      aboutImage2: image2,
      aboutImage1: image1,
    };
  },
  components: {
    SwiperView,
    PartnerSwiper,
    HeadingTitle,
    HeaderImage,
    IntroBlock,
    SolutionBlock,
    PopupModal,
    TeamExpartBlock,
    // IntroBlockImage
  },

  mounted() {
    window.scrollTo(0, 0);
  },

  methods: {
    solutionView(data) {
      this.solution = data;
      this.show = true;
    },
    closeView() {
      this.show = false;
    },
  },
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

.text-color {
  color: red;
}
</style>
