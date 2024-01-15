<template>
  <div class="home -mt-10">
    <HeaderImage title="Services" :backgroundImage="backgroundImage" />
    <div class="section relative">
      <ServiceBlock :ourServices="ourServices" @serviceView="serviceView" />

      <PopupModal v-if="show" :socialLinks="socialLinks" :popupview="service" @closeView="closeView" />
    </div>

    <!-- contact information -->
    <div class="section px-12">
      <div class="service-cover">
        <ServiceContact :tag="tag" :title="title" :contact="contact" />
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
  </div>
</template>

<script>
import SwiperView from "@/components/swiper/SwiperView.vue";
import PartnerSwiper from "@/components/swiper/PartnerSwiper.vue";
import ServiceBlock from "@/components/card/ServiceBlock.vue";
import HeadingTitle from "@/components/main/HeadingTitle";
import HeaderImage from "@/components/main/HeaderImage.vue";
import { ourServices, socialLinks } from "@/jsonStore/store";
import ServiceContact from "@/components/main/ServiceContact.vue";
import PopupModal from "@/components/modal/PopupModal";

export default {
  data() {
    return {
      backgroundImage: "home-header",
      show: false,
      service: {},
      ourServices: ourServices,
      socialLinks: socialLinks,
      contact: "+8801600000000",
      title: " Call Us For Any inquiry",
      tag: "To make requests for further information, contact us",
    };
  },

  components: {
    SwiperView,
    PartnerSwiper,
    ServiceBlock,
    HeadingTitle,
    HeaderImage,
    ServiceContact,
    PopupModal,
  },

  mounted() {
    window.scrollTo(0, 0);
  },

  methods: {
    serviceView(data) {
      this.service = data;
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
  background-image: url("../assets/images/about.jpg");
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}

.service-cover {
  background-image: url("../assets/services/background.jpg");
  /* background-position: center; */
  background-size: cover;
  object-fit: cover;
  border-radius: 10px;
}
</style>