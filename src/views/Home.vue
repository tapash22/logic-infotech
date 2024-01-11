<template>
  <div class="home -mt-10">
    <div class="home-header home-banner">
      <div class="banner-block">
        <span class="home-banner-title user-select-none">
          We provide the most advance digital solution
        </span>
        <p class="home-banner-subtitle user-select-none">
          Leading Software Development Studio & Agency
        </p>
        <div class="home-banner-icon-section">
          <div class="home-banner-icon-block" @click="showView">
            <i class="fa fa-play home-banner-icon" aria-hidden="true"></i>
          </div>
          <p class="home-banner-icon-text user-select-none">Watch Video</p>
        </div>
      </div>
    </div>
    <!-- intro part -->
    <div class="flex px-5 section">
      <!-- left side -->
      <IntroBlock :title="title" :subtitle="subtitle" :introText="introText" :introBox="introBox" :introduce="introduce"/>
      <!-- left end -->
      <!-- right side -->
      <div class="w-1/2 h-auto flex justify-center items-end">
        <div
          class="w-full h-2/3 px-2 relative bg-gray-300 opacity-90 rounded-xl"
        >
          <div class="absolute right-0 bottom-4">
            <img
              src="../assets/about-big.jpg"
              class="object-cover w-full h-full rounded-lg"
            />
          </div>
          <div class="absolute bottom-0 -left-4">
            <img
              src="../assets/about-sm.jpg"
              class="object-cover w-full h-auto rounded-lg"
            />
          </div>
        </div>
      </div>
      <!-- right side end -->
    </div>
    <!-- intro part end -->

    <!-- product list -->
    <div class="section">
      <span class="section-title user-select-none"> WHAT WE PROVIDE </span>
      <p class="section-subtitle user-select-none">
        We provide truly prominent Software solutions
      </p>
      <ProductCard :cardView="cardView" />
    </div>
    <!-- product list end -->

    <!-- client part -->
    <div class="section">
      <span class="section-title user-select-none"> PROJECTS </span>
      <p class="section-subtitle user-select-none">Our valuable client</p>
      <div class="px-8 py-3">
        <PartnerSwiper />
      </div>
    </div>
    <!-- client part end -->

    <!-- testimonial part -->
    <div class="bg-gray-300 section">
      <HeadingTitle title="TESTIMONIAL" subtitle="20k+ satisfied clients worldwide" />
      <div class="px-12 py-3">
        <SwiperView />
      </div>
    </div>
    <!-- testimonial part end -->

    <!-- contact block -->
    <div class="flex section px-5">
      <ContactInformation title="To make requests for further information, contact us" :information="information" />
      <div class="message-section">
       <ContactForm :formInput="formInput" :formTextarea="formTextarea" :buttonClass="buttonClass" title="LEAVE US MASSAGE" subtitle="How May We Help You!"/>
      </div>
    </div>
    <!-- contact block end -->

    <!-- popup video -->
    <div class="fixed inset-0 flex justify-center items-center" v-if="show">
      <div
        class="absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-red-700 shadow-xl shadow-red-500 flex justify-center items-center"
      >
        <VideoPlayer :videoUrl="youtubeVideoUrl" />
        <div
          class="absolute -right-4 -top-4 w-10 h-10 flex justify-center items-center bg-white rounded-full cursor-pointer"
          @click="hideView"
        >
          <i class="fa fa-times text-xl font-normal"></i>
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
import ContactForm from '@/components/form/ContactForm'
import IntroBlock from "@/components/card/IntroBlock.vue";
// import { introduce,information,cardView } from '../jsonStore/store';

export default {
  name: "Home",
  data() {
    return {
      title:"WHO WE ARE",
      subtitle:"We run all kinds of software services that vow your success",
      introText:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos modi tenetur, amet eveniet a placeat voluptatum natus doloremque cumque cupiditate adipisci officia alias, illo voluptate unde veniam maxime accusantium. Nam.",
      introBox:{
        icon:'fa fa-share',
        details:"Accelerate innovation with world-class tech teams We’ll match you to an entire remote."
      },
      buttonClass: 'form-button',
     formInput:'form-input',
     formTextarea:'form-textarea',
      show: false,
      youtubeVideoUrl: "https://www.youtube.com/embed/Wy9q22isx3U",
      introduce: [
        {
          id: 1,
          name: "Expert Team",
          icon:'fa fa-arrow-right',
          details: "Accelerate innovation with world-class tech teams",
        },
        {
          id: 2,
          name: "Custom Code",
          icon:'fa fa-arrow-right',
          details: "Accelerate innovation with world-class tech teams",
        },
      ],

      information: [
        {
          id: 1,
          property: "Contact Number",
          value: "+00(1) 123 456 7890",
          icon: "fa fa-phone",
        },
        {
          id: 2,
          property: "Our Mail",
          value: "info@logicinfotech.com",
          icon: "fa fa-envelope-o ",
        },
        {
          id: 3,
          property: "Our Location",
          value:
            "House - 85, Road - 04, Block - B, Banani, Dhaka - 1213. Bangladesh",
          icon: "fa fa-map-marker",
        },
      ],

      cardView: [
        {
          id: 1,
          name: "Web Development",
          text: "Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team ",
          icon: "fa fa-code",
          carddetails: [
            {
              id: 1,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/demo1.jpg"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
            {
              id: 2,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/demo2.jpg"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
            {
              id: 3,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/demo1.jpg"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
          ],
        },
        {
          id: 2,
          name: "Mobile App Development",
          text: "Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team ",
          icon: "fa fa-gamepad",
          carddetails: [
            {
              id: 1,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/erp.png"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
            {
              id: 2,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/dms.png"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
            {
              id: 3,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/erp.png"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
          ],
        },
        {
          id: 3,
          name: "Software Innovation",
          text: "Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team ",
          icon: "fa fa-rocket",
          carddetails: [
            {
              id: 1,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/demo1.jpg"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
            {
              id: 2,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/demo1.jpg"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
            {
              id: 3,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/demo1.jpg"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
          ],
        },
        {
          id: 4,
          name: "App Management System",
          text: "Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team",
          icon: "fa fa-television",
          carddetails: [
            {
              id: 1,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/erp.png"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
            {
              id: 2,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/dms.png"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
            {
              id: 3,
              name: "Name of product",
              link: "",
              image: require("../assets/demo/erp.png"),
              message:
                "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum veritatis explicabo praesentium voluptate ipsam obcaecati placeat omnis facere eaque corporis? Iste eligendi omnis similique dolor suscipit maxime beatae quibusdam sed.",
            },
          ],
        },
      ],
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
    IntroBlock
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
      console.log("click action");
    },
    hideView() {
      (this.show = false), console.log("hide view");
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap");

.home-header {
  /* background-image: url("../assets/images/hero2-bg.jpg"); */
  background-image: url("../assets/images/1.jpg");
  /* background-image: url("../assets/images/2.jpg"); */
  /* background-image: url("../assets/images/3.jpg"); */
  background-size: cover;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>
