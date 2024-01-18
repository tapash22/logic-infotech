<template>
  <div>
    <carousel
      :autoplay="true"
      :navigation-enabled="false"
      :pagination-enabled="true"
      :easing="'ease'"
      :pagination-color="'#808080'"
      :pagination-padding="12"
      :pagination-active-color="'#84053D'"
      :perPageCustom="[
        [370, 1],
        [480, 2],
        [768, 2],
      ]"
    >
      <slide v-for="clientT in Clienttestemonial" :key="clientT.id">
        <div class="swiper-wrapper">
          <div class="swiper-block">
            <div class="swiper-block-image">
              <img :src="clientT.image" class="swiper-block-image-view" />
            </div>
            <div class="swiper-block-details">
              <i class="fa fa-comments-o swiper-block-details-icon"></i>
              <p class="swiper-block-details-message">
                {{ clientT.messages }}
              </p>
              <p class="swiper-block-details-client-name">
                {{ clientT.name }}
                <span class="swiper-block-details-client-designation"
                  >/ {{ clientT.designation }}</span
                >
              </p>
            </div>
          </div>
        </div>
      </slide>
    </carousel>
  </div>
</template>
  
  <script>
import { Carousel, Slide } from "vue-carousel";
import { Clienttestemonial } from "../../jsonStore/store";

export default {
  data() {
    return {
      Clienttestemonial: Clienttestemonial,
      $mq: {
        mobile: false,
      },
    };
  },

  components: {
    Carousel,
    Slide,
  },
  computed: {
    perPage() {
      return this.$mq.mobile ? 1 : 2; // Adjust the breakpoint as needed
    },
  },
  mounted() {
    // Add an event listener for window resize
    window.addEventListener("resize", this.handleResize);
    // Initial calculation
    this.handleResize();
  },
  beforeDestroy() {
    // Remove the event listener to prevent memory leaks
    window.removeEventListener("resize", this.handleResize);
  },
  methods: {
    handleResize() {
      // Update the window width in the $mq property
      this.$mq = {
        mobile: window.innerWidth < 768, // Adjust the breakpoint as needed
      };
    },
  },
};
</script>
  
  <style >
.VueCarousel-pagination {
  width: 100%;
  text-align: center;
  margin-top: -50px;
}
.carousel-pagination-bullet {
  margin: 0 2px; /* Adjust the margin as needed */
}

/* Example: Add some space between pagination bullets */
.carousel-pagination {
  padding: 5px;
}
</style>
  