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
      <div class="intro-block-right">
        <span class="intro-block-right-title">
          WHO WE ARE
        </span>
        <p
          class="intro-block-right-subtitle"
        >
          We run all kinds of software services that vow your success
        </p>
        <p
          class="intro-block-right-text"
        >
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos modi
          tenetur, amet eveniet a placeat voluptatum natus doloremque cumque
          cupiditate adipisci officia alias, illo voluptate unde veniam maxime
          accusantium. Nam.
        </p>

        <!-- last part -->
        <div class="intro-block-bottom">
          <div
            class="intro-block-bottom-card"
            v-for="intro in introduce"
            :key="intro.id"
          >
            <div class="intro-block-bottom-card-first">
              <span class="intro-block-bottom-card-first-title">
                {{ intro.name }}
              </span>
            </div>
            <p
              class="intro-block-bottom-card-first-details"
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
      <div class="intro-block-product">
        <div v-for="ours in ourSolution" :key="ours.id" class="intro-block-product-card">
          <div class="product-icon-block py-3">
           <img :src="ours.image" />
          </div>
          <p class="product-type">
            {{ ours.title }}
          </p>
          <p class="product-details">
            {{ours.details}}
          </p>
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

export default {
  data() {
    return {
      backgroundImage:'home-header',
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
      ourTeams: [
        {
          id: 1,
          image: require("../assets/images/testi-1.jpg"),
          name: "Tapash paul",
          designation: "Frontend Developer",
          social: [
            "fa fa-facebook-square",
            "fa fa-linkedin",
            "fa fa-instagram",
          ],
        },
        {
          id: 2,
          image: require("../assets/images/testi-2.jpg"),
          name: "Tapash paul",
          designation: "Frontend Developer",
          social: [
            "fa fa-facebook-square",
            "fa fa-linkedin",
            "fa fa-instagram",
          ],
        },
        {
          id: 3,
          image: require("../assets/images/testi-1.jpg"),
          name: "Tapash paul",
          designation: "Frontend Developer",
          social: [
            "fa fa-facebook-square",
            "fa fa-linkedin",
            "fa fa-instagram",
          ],
        },
        {
          id: 4,
          image: require("../assets/images/testi-2.jpg"),
          name: "Tapash paul",
          designation: "Frontend Developer",
          social: [
            "fa fa-facebook-square",
            "fa fa-linkedin",
            "fa fa-instagram",
          ],
        },
      ],

      ourSolution:[
        {
          id:1,
          title:'Infrustructure Technology',
          image:require('../assets/icon-image/1.png'),
          details:'Accelerate innovation with world-class tech teams We’ll match you to an entire.'
        },
        {
          id:2,
          title:'Highly professional team members',
          image:require('../assets/icon-image/2.png'),
          details:'Accelerate innovation with world-class tech teams We’ll match you to an entire.'
        },
        {
          id:3,
          title:'Security Management',
          image:require('../assets/icon-image/3.png'),
          details:'Accelerate innovation with world-class tech teams We’ll match you to an entire.'
        },
        {
          id:4,
          title:'Desktop Computing',
          image:require('../assets/icon-image/4.png'),
          details:'Accelerate innovation with world-class tech teams We’ll match you to an entire.'
        },
        {
          id:5,
          title:'Infrustructure Technology',
          image:require('../assets/icon-image/5.png'),
          details:'Accelerate innovation with world-class tech teams We’ll match you to an entire.'
        },
        {
          id:6,
          title:'Ideas for high return investment',
          image:require('../assets/icon-image/6.png'),
          details:'Accelerate innovation with world-class tech teams We’ll match you to an entire.'
        },
        {
          id:7,
          title:'Fully high IT Managment',
          image:require('../assets/icon-image/7.png'),
          details:'Accelerate innovation with world-class tech teams We’ll match you to an entire.'
        },
        {
          id:8,
          title:'Data secure & Managment',
          image:require('../assets/icon-image/8.png'),
          details:'Accelerate innovation with world-class tech teams We’ll match you to an entire.'
        },
      ]
    };
  },
  components: {
    SwiperView,
    PartnerSwiper,
    HeadingTitle,
    HeaderImage
  },

  mounted(){
        window.scrollTo(0,0)
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
</style>
