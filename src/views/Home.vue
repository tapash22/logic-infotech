<template>
  <div class="home">
    <HomeBanner
      :title="bannerTitle"
      :subtitle="bannerSubtitle"
      :button="bannerButton"
      @showView="showView"
    />
    <!-- intro part -->
    <div class="home-intro-wrapper section">
      <IntroBlock
        :title="title"
        :subtitle="subtitle"
        :introText="introText"
        :introBox="introBox"
        :introduce="introduce"
      />
      <IntroBlockImage :introImage1="introImage1" :introImage2="introImage2" />
    </div>
    <!-- intro part end -->

    <!-- product list -->
    <div class="section">
      <HeadingTitle
        title="WHAT WE PROVIDE"
        subtitle="We provide truly prominent Software solutions"
      />
      <ProductCard :cardView="cardView" />
    </div>
    <!-- product list end -->

    <!-- client part -->
    <div class="section">
      <HeadingTitle title="PROJECTS" subtitle="Our valuable client" />
      <div class="partner-view">
        <PartnerSwiper />
      </div>
    </div>
    <!-- client part end -->

    <!-- testimonial part -->
    <div class="bg-gray-300 section">
      <HeadingTitle
        title="TESTIMONIAL"
        subtitle="20k+ satisfied clients worldwide"
      />
      <div class="swiper-view">
        <SwiperView />
      </div>
    </div>
    <!-- testimonial part end -->

    <!-- contact block -->
    <div class="section home-intro-wrapper">
      <ContactInformation
        title="To make requests for further information, contact us"
        :information="information"
      />
      <div class="message-section">
        <ContactForm
          :formInput="formInput"
          :formTextarea="formTextarea"
          :buttonClass="buttonClass"
          title="LEAVE US MASSAGE"
          subtitle="How May We Help You!"
        />
      </div>
    </div>
    <!-- contact block end -->

    <!-- popup video -->
    <div class="home-popup-wrapper" v-if="show">
      <div class="home-popup-block">
        <VideoPlayer :videoUrl="youtubeVideoUrl" />
        <div class="home-popup-close" @click="hideView">
          <i class="fa fa-times home-close-icon"></i>
        </div>
      </div>
    </div>

    <!-- popup video end -->
  </div>
</template>

<script>
import SwiperView from "@/components/swiper/SwiperView.vue";
import PartnerSwiper from "@/components/swiper/PartnerSwiper.vue";
import ProductCard from "@/components/card/ProductCard";
import VideoPlayer from "@/components/videobox/VideoPlayer";
import HeadingTitle from "@/components/main/HeadingTitle.vue";
import ContactInformation from "@/components/main/ContactInformation.vue";
import ContactForm from "@/components/form/ContactForm";
import IntroBlock from "@/components/card/IntroBlock.vue";
import HomeBanner from "@/components/main/HomeBanner.vue";
// import Slider from "@/components/slider/Slider.vue"
import { introduce1, information, cardView } from "../jsonStore/store";
import IntroBlockImage from "@/components/card/IntroBlockImage.vue";

export default {
  name: "Home",
  data() {
    return {
      bannerTitle: " We provide the most advance digital solution",
      bannerSubtitle: "Leading Software Development Studio & Agency",
      bannerButton: "Watch Video",
      title: "WHO WE ARE",
      subtitle: "We run all kinds of software services that vow your success",
      introText:
        "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos modi tenetur, amet eveniet a placeat voluptatum natus doloremque cumque cupiditate adipisci officia alias, illo voluptate unde veniam maxime accusantium. Nam.",
      introBox: {
        icon: "fa fa-share",
        details:
          "Accelerate innovation with world-class tech teams We’ll match you to an entire remote.",
      },
      buttonClass: "form-button",
      formInput: "form-input",
      formTextarea: "form-textarea",
      show: false,
      youtubeVideoUrl: "https://www.youtube.com/embed/Wy9q22isx3U",
      introduce: introduce1,
      information: information,
      cardView: cardView,
      introImage1: require("../assets/about-big.jpg"),
      introImage2: require("../assets/about-sm.jpg"),
    };
  },
  components: {
    SwiperView,
    PartnerSwiper,
    ProductCard,
    VideoPlayer,
    HeadingTitle,
    ContactInformation,
    ContactForm,
    IntroBlock,
    HomeBanner,
    IntroBlockImage,
    // Slider
  },

  mounted() {
    window.scrollTo(0, 0);
  },

  methods: {
    mailSubmit(e) {
      e.preventDefault();
      console.log(this.mailForm);
    },

    showView() {
      this.show = true;
    },
    hideView() {
      this.show = false;
    },
  },
};
</script>

