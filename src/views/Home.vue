<template>
  <div class="home block">
    <div class="block w-full h-auto px-5 py-10">
      <span class="text-sm font-normal tracking-wide flex justify-center">
        WHAT WE PROVIDE
      </span>
      <p class="text-3xl font-bold tracking-wide py-2 flex justify-center">
        We provide truly prominent Software solutions.
      </p>
      <div
        class="py-3 w-full h-auto flex justify-center gap-5 px-5 "
      >
      <div class="rounded-lg bg-gray-300 px-3 py-4 shadow-sm shadow-gray-300 block" v-for="cardv in cardView" :key="cardv.id">
        <i class="w-20 h-20 rounded-full p-1 text-5xl bg-indigo-950 font-bold text-white flex justify-center items-center my-2 " :class="cardv.icon">

        </i>
        <p class="text-2xl font-bold py-2 tracking-normal text-black leading-7">
          {{ cardv.name }}
        </p>
        <p class="text-sm font-medium py-3 px-1 tracking-normal text-black text-justify">
          {{ cardv.text }}
        </p>
      </div>
      </div>
    </div>

    <div class="w-full h-auto px-0 py-10 bg-white bloack">
      <span class="text-sm font-normal tracking-wide flex justify-center w-full ">
        PROJECTS
      </span>
      <p class="text-3xl font-bold tracking-wide py-2 flex justify-center w-full ">
        Our valuable client
      </p>
      <div class="px-8 py-3 ">
        <PartnerSwiper/>
      </div>
    </div>

    <div class="w-full h-auto px-0 py-10 bg-gray-300 bloack">
      <span class="text-sm font-normal tracking-wide flex justify-center w-full ">
        TESTIMONIAL
      </span>
      <p class="text-3xl font-bold tracking-wide py-2 flex justify-center w-full ">
        20k+ satisfied clients worldwide
      </p>
      <div class="px-8 py-3 ">
        <Swiper />
      </div>
    </div>

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
import Swiper from '@/components/swiper/SwiperView.vue';
import PartnerSwiper from '@/components/swiper/PartnerSwiper.vue';

export default {
  name: "Home",

  data() {
    return {
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

      cardView:[
        {
          id:1,
          name:'Web Development',
          text:'Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team ',
          icon:'fa fa-code'
        },
        {
          id:2,
          name:'Mobile App Development',
          text:'Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team ',
          icon:'fa fa-gamepad'
        },
        {
          id:3,
          name:'Software Innovation',
          text:'Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team ',
          icon:'fa fa-rocket'
        },
        {
          id:4,
          name:'App Management System',
          text:'Accelerate innovation with world-class tech teams We’ll match you to an entire remote team  match you to an entire remote team',
          icon:'fa fa-television'
        },
      ]
    };
  },
  components: {
    Swiper,
    PartnerSwiper
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
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap');

/* input::placeholder,
textarea::placeholder {
  font-size: 12px;
  font-weight: 500;
  color: gray;
  letter-spacing: 1px;
} */
</style>
