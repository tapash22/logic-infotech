<template>
  <div>
    <carousel
      :autoplay="true"
      :show-pagination="true"
      :per-page="6"
      :loop="true"
      :interval="100"
      :pagination-class="'custom-pagination'"
      :pagination-active-class="'custom-pagination-active'"
    >
      <slide v-for="partner in partners" :key="partner.id">
        <div class="py-3">
          <div
            class="partner-image-block"
          >
            <img
              :src="partner.image"
              class="partner-image-block-view"
            />
          </div>
        </div>
      </slide>
    </carousel>
  </div>
</template>
  
  <script>
import { Carousel, Slide } from "vue-carousel";
import { partners } from "../../jsonStore/store";

export default {
  data() {
    return {
      partners: partners
    };
  },
  components: {
    Carousel,
    Slide,
  },
};
</script>
  
<style >
.VueCarousel-dot {
  visibility: hidden;
}
</style>
  