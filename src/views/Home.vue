<template>
  <div class="home block -mt-16">
    <div class="flex w-full justify-start items-center  px-14 home-header">
      <div class="block w-1/2 py-5">
<span class="text-lg font-medium tracking-wide py-3 text-white">
  We provide the most advance digital solution
</span>
<p class="border-l-4 border-indigo-500 text-5xl font-bold my-4 px-2 text-white">
  Leading Software Development Studio & Agency
</p>
<div class="flex justify-start my-3 gap-3">
  <div class="w-20 h-20 rounded-full ring-1 ring-white flex justify-center items-center">
    <i class="fa fa-play bg-white rounded-full w-16 h-16 flex justify-center items-center text-xl text-gray-600" aria-hidden="true"></i>
  </div>
  <p class="text-2xl font-bold flex justify-center items-center text-white ">
    Watch Video
  </p>
</div>
      </div>
    </div>
    <!-- intro part -->
    <div class="flex w-full h-auto px-14 py-10">
      <!-- left side -->
      <div class="w-1/2 h-auto pr-32 block">
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

        <div class="px-3 py-5 bg-gray-300 rounded-lg flex justify-center my-4">
          <!-- <span class="text-3xl font-bold text-indigo-950 px-2">	&#34;</span> -->
          <i
            class="fa fa-share text-3xl font-bold text-indigo-950 px-2 flex items-center"
            aria-hidden="true"
          ></i>
          <p
            class="text-lg font-bold px-2 tracking-wide text-center text-indigo-950"
          >
            Accelerate innovation with world-class tech teams We’ll match you to
            an entire remote.
          </p>
        </div>
        <!-- last part -->
        <div class="w-full my-3 px-3 flex justify-between gap-5">
          <div
            class="block bg-gray-200 rounded-lg py-3 px-3"
            v-for="intro in introduce"
            :key="intro.id"
          >
            <div class="flex justify-center">
              <i
                class="fa fa-arrow-right text-sm w-6 h-6 mx-1 bg-indigo-950 rounded-full text-white flex justify-center items-center"
                aria-hidden="true"
              ></i>
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
    <div class="block w-full h-auto px-5 py-10">
      <span class="text-sm font-normal tracking-wide flex justify-center">
        WHAT WE PROVIDE
      </span>
      <p class="text-3xl font-bold tracking-wide py-2 flex justify-center">
        We provide truly prominent Software solutions.
      </p>
      <div class="py-3 w-full h-auto flex justify-center gap-5 px-5">
        <div
          class="product-card rounded-lg bg-gray-300 px-3 py-4 shadow-sm shadow-gray-300 block scale-100 hover:scale-110 transition-all delay-100 cursor-pointer"
          v-for="cardv in cardView"
          :key="cardv.id"
        >
          <div class="flex justify-start w-full">
            <i
              class="icon-card w-20 h-20 rounded-full p-1 text-5xl bg-indigo-950 font-bold text-white flex justify-center items-center my-2"
              :class="cardv.icon"
            >
            </i>
          </div>
          <p
            class="text-2xl font-bold py-2 tracking-normal text-black leading-7"
          >
            {{ cardv.name }}
          </p>
          <p
            class="text-sm font-medium py-3 px-1 tracking-normal text-black text-justify"
          >
            {{ cardv.text }}
          </p>
        </div>
      </div>
    </div>
    <!-- product list end -->

    <!-- client part -->
    <div class="w-full h-auto px-0 py-10 bg-white bloack">
      <span
        class="text-sm font-normal tracking-wide flex justify-center w-full"
      >
        PROJECTS
      </span>
      <p
        class="text-3xl font-bold tracking-wide py-2 flex justify-center w-full"
      >
        Our valuable client
      </p>
      <div class="px-8 py-3">
        <PartnerSwiper />
      </div>
    </div>
    <!-- client part end -->

    <!-- testimonial part -->
    <div class="w-full h-auto px-0 py-10 bg-gray-300 bloack">
      <span
        class="text-sm font-normal tracking-wide flex justify-center w-full"
      >
        TESTIMONIAL
      </span>
      <p
        class="text-3xl font-bold tracking-wide py-2 flex justify-center w-full"
      >
        20k+ satisfied clients worldwide
      </p>
      <div class="px-8 py-3">
        <Swiper />
      </div>
    </div>
    <!-- testimonial part end -->

    <!-- contact block -->
    <div class="flex w-full h-auto px-5 py-10">
      <!-- left side -->
      <div class="w-1/2 h-auto block">
        <h1
          class="font-bold tracking-wide flex justify-start px-2 text-3xl border-l-4 border-indigo-500 mr-36 mb-5"
        >
          To make requests for further information, contact us
        </h1>
        <div
          class="flex w-full my-2 py-3 px-2"
          v-for="info in information"
          :key="info.id"
        >
          <div class="w-1/4 h-auto flex justify-center items-center">
            <i
              :class="info.icon"
              class="text-6xl fonr-bold text-indigo-950"
            ></i>
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
      <!-- left side end -->

      <!-- right side -->
      <div
        class="w-1/2 h-auto bg-gray-300 py-4 flex justify-center items-center rounded-lg"
      >
        <form class="w-full px-5 py-2 block" @submit="mailSubmit">
          <span
            class="text-sm uppercase font-normal tracking-wider flex justify-center"
            >LEAVE US MASSAGE</span
          >
          <h1 class="font-bold tracking-wide flex justify-center text-2xl">
            How May We Help You!
          </h1>
          <div class="block">
            <label class="w-full py-2 text-sm font-medium tracking-wide"
              >Name</label
            >
            <input
              type="text"
              v-model="mailForm.name"
              class="h-10 w-full bg-white rounded-lg py-2 px-2 text-sm font-bold tracking-wide"
              placeholder="Full Name"
            />
          </div>
          <div class="block">
            <label class="w-full py-2 text-sm font-bold tracking-wide"
              >Email</label
            >
            <input
              type="text"
              v-model="mailForm.email"
              class="h-10 w-full bg-white rounded-lg py-2 px-2 text-sm font-bold tracking-wide"
              placeholder="Email"
            />
          </div>
          <div class="block">
            <label class="w-full py-2 text-sm font-bold tracking-wide"
              >Subject</label
            >
            <input
              type="text"
              v-model="mailForm.subject"
              class="h-10 w-full bg-white rounded-lg py-2 px-2 text-sm font-bold tracking-wide"
              placeholder="Subject"
            />
          </div>
          <div class="block">
            <label class="w-full py-2 text-sm font-bold tracking-wide"
              >Message</label
            >
            <textarea
              v-model="mailForm.message"
              class="w-full py-2 px-2 text-sm font-bold tracking-wide h-auto"
              placeholder="Write A Message"
            >
            </textarea>
          </div>
          <div class="w-full py-2 block">
            <button
              class="text-sm font-bold bg-gray-600 text-white w-full py-3 rounded-lg"
              type="submit"
            >
              Send Message
            </button>
          </div>
        </form>
      </div>
      <!-- right side end -->
    </div>
    <!-- contact block end -->
  </div>
</template>

<script>
import Swiper from "@/components/swiper/SwiperView.vue";
import PartnerSwiper from "@/components/swiper/PartnerSwiper.vue";

export default {
  name: "Home",

  data() {
    return {
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
      mailForm: {
        name: "",
        email: "",
        subject: "",
        message: "",
      },
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
    Swiper,
    PartnerSwiper,
  },

  methods: {
    mailSubmit(e) {
      e.preventDefault();
      console.log(this.mailForm);
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap");

/* .navigation{
  background: yellow;
} */
.product-card:hover i {
  transform: translateX(100%);
}

.home-header{
  background-image: url('../assets/images/hero2-bg.jpg');

  border-bottom-left-radius: 50%;
  border-bottom-right-radius: 50%;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>
