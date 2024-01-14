<template>
  <div>
    <carousel :autoplay="true">
      <slide
        v-for="clientT in Clienttestemonial"
        :key="clientT.id"
        :per-page="2"
        :loop="true"
        :space-padding="0"
        class="py-3"
        :paginationPadding="5"
      >
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
    };
  },

  components: {
    Carousel,
    Slide,
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
  