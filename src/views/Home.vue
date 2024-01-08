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
          <p class="home-banner-icon-text user-select-none">
            Watch Video
          </p>
        </div>
      </div>
    </div>
    <!-- intro part -->
    <div class="flex px-5 section">
      <!-- left side -->
      <div class="w-1/2 h-auto pr-32 block">
        <span class="text-sm font-normal tracking-wide flex justify-start">
          WHO WE ARE
        </span>
        <p class="text-5xl font-bold tracking-normal py-3 flex justify-center leading-none">
          We run all kinds of software services that vow your success
        </p>
        <p class="text-sm font-medium tracking-normal text-justify break-words leading-7 py-2">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos modi
          tenetur, amet eveniet a placeat voluptatum natus doloremque cumque
          cupiditate adipisci officia alias, illo voluptate unde veniam maxime
          accusantium. Nam.
        </p>

        <div class="px-3 py-5 bg-gray-300 rounded-lg flex justify-center my-4">
          <!-- <span class="text-3xl font-bold text-indigo-950 px-2">	&#34;</span> -->
          <i class="fa fa-share text-3xl font-bold text-indigo-950 px-2 flex items-center" aria-hidden="true"></i>
          <p class="text-lg font-bold px-2 tracking-wide text-center text-indigo-950">
            Accelerate innovation with world-class tech teams We’ll match you to
            an entire remote.
          </p>
        </div>
        <!-- last part -->
        <div class="w-full my-3 px-3 flex justify-between gap-5">
          <div class="block bg-gray-200 rounded-lg py-3 px-3" v-for="intro in introduce" :key="intro.id">
            <div class="flex justify-center">
              <i class="fa fa-arrow-right text-sm w-6 h-6 mx-1 bg-indigo-950 rounded-full text-white flex justify-center items-center"
                aria-hidden="true"></i>
              <span class="tracking-wide text-black text-lg font-bold">
                {{ intro.name }}
              </span>
            </div>
            <p class="text-sm font-normal text-indigo-950 flex justify-center text-justify py-2">
              {{ intro.details }}
            </p>
          </div>
        </div>
        <!-- last part end -->
      </div>
      <!-- left end -->

      <!-- right side -->
      <div class="w-1/2 h-auto flex justify-center items-end">
        <div class="w-full h-2/3 px-2 relative bg-gray-300 opacity-90 rounded-xl">
          <div class="absolute right-0 bottom-4">
            <img src="../assets/about-big.jpg" class="object-cover w-full h-full rounded-lg" />
          </div>
          <div class="absolute bottom-0 -left-4">
            <img src="../assets/about-sm.jpg" class="object-cover w-full h-auto rounded-lg" />
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
    <div class="section ">
      <span class="section-title user-select-none"> PROJECTS </span>
      <p class="section-subtitle user-select-none">Our valuable client</p>
      <div class="px-8 py-3">
        <PartnerSwiper />
      </div>
    </div>
    <!-- client part end -->

    <!-- testimonial part -->
    <div class=" bg-gray-300 section ">
      <span class="section-title user-select-none"> TESTIMONIAL </span>
      <p class="section-subtitle user-select-none">
        20k+ satisfied clients worldwide
      </p>
      <div class="px-12 py-3">
        <SwiperView />
      </div>
    </div>
    <!-- testimonial part end -->

    <!-- contact block -->
    <div class="flex section px-5">
      <div class="w-1/2 h-auto block px-3 py-3">
        <h1
          class="font-bold tracking-wide flex justify-start px-2 text-3xl border-l-4 border-indigo-500 mr-36 mb-5 user-select-none">
          To make requests for further information, contact us
        </h1>
        <div class="flex w-full my-2 py-3 px-2" v-for="info in information" :key="info.id">
          <div class="w-1/4 h-auto flex justify-center items-center">
            <i :class="info.icon" class="text-6xl fonr-bold text-indigo-950"></i>
          </div>
          <div class="w-2/4 block px-1">
            <h3 class="font-bold tracking-normal flex justify-start text-2xl">
              {{ info.property }}
            </h3>
            <p class="break-all text-sm font-bold text-black mr-16">
              {{ info.value }}
            </p>
          </div>
        </div>
      </div>
      <div class="message-section">
        <form class="submit-form" @submit="mailSubmit">
          <span class="form-title">LEAVE US MASSAGE</span>
          <h1 class="form-subtitle">How May We Help You!</h1>
          <div class="block">
            <label class="form-label">Name</label>
            <input type="text" v-model="mailForm.name" class="form-input" placeholder="Full Name" />
          </div>
          <div class="block">
            <label class="form-label">Email</label>
            <input type="text" v-model="mailForm.email" class="form-input" placeholder="Email" />
          </div>
          <div class="block">
            <label class="form-label">Subject</label>
            <input type="text" v-model="mailForm.subject" class="form-input" placeholder="Subject" />
          </div>
          <div class="block">
            <label class="form-label">Message</label>
            <textarea v-model="mailForm.message" class="form-textarea" placeholder="Write A Message">
            </textarea>
          </div>
          <div class="w-full py-2 block">
            <button class="form-button" type="submit">Send Message</button>
          </div>
        </form>
      </div>
    </div>

    <div class="absolute left-1/4 top-1/3 bg-red-700 shadow-xl shadow-red-500 flex justify-center items-center" v-if="show">
      <VideoPlayer :videoUrl="youtubeVideoUrl" />
      <div class="absolute -right-3 -top-3 w-10 h-10 flex justify-center align-middle bg-white rounded-xl text-red-900 cursor-pointer font-bold text-2xl" @click="hideView">
        X
      </div>
    </div>
    <!-- contact block end -->
  </div>
</template>

<script>
import SwiperView from "@/components/swiper/SwiperView.vue";
import PartnerSwiper from "@/components/swiper/PartnerSwiper.vue";
import ProductCard from '@/components/card/ProductCard';
import VideoPlayer from '@/components/videobox/VideoPlayer'
// import { introduce,information,cardView } from '../jsonStore/store';

export default {
  name: "Home",

  data() {
    return {
      show:false,
      youtubeVideoUrl: "https://www.youtube.com/embed/Wy9q22isx3U",
      mailForm: {
        name: "",
        email: "",
        subject: "",
        message: "",
      },

      introduce: [
        {
          id: 1,
          name: "Expert Team",
          details: "Accelerate innovation with world-class tech teams",
        },
        {
          id: 2,
          name: "Custom Code",
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
        },
        {
          id: 2,
          name: "Mobile App Development",
          text: "Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team ",
          icon: "fa fa-gamepad",
        },
        {
          id: 3,
          name: "Software Innovation",
          text: "Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team ",
          icon: "fa fa-rocket",
        },
        {
          id: 4,
          name: "App Management System",
          text: "Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team",
          icon: "fa fa-television",
        },
      ],
    };
  },
  components: {
    SwiperView,
    PartnerSwiper,
    ProductCard,
    VideoPlayer
  },

  mounted() {
    window.scrollTo(0, 0)
  },

  methods: {
    mailSubmit(e) {
      e.preventDefault();
      console.log(this.mailForm);
    },

    showView(){
      this.show = true;
      console.log("click action")
    },
    hideView(){
      this.show = false,
      console.log("hide view");
    }
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
