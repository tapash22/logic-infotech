<template>
  <div>
    <carousel :autoplay="true">
      <slide
        v-for="i in 10"
        :key="i"
        :per-page="2"
        :loop="true"
        :space-padding="0"
        class="py-3"
        :paginationPadding="5"
      >
        <div class="flex justify-center py-3 px-5 bg-transparent">
          <div
            class="flex bg-white relative rounded-lg shadow-xl shadow-gray-700"
          >
            <div class="w-1/3 h-auto flex justify-start items-center">
              <img
                src="../../assets/images/hero2-bg.jpg"
                class="ring-2 ring-indigo-900 -ml-7 rounded-lg"
              />
            </div>
            <div class="w-2/3 px-3 py-5 block">
              <i class="fa fa-comments-o text-5xl text-indigo-900 px-2"></i>
              <p class="text-lg font-medium tracking-wide py-2 px-2 text-black text-justify">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore,
                optio nemo fuga reprehenderit sapiente officia sequi eos ullam
                ipsam. Id sit placeat sed in quod dolorem, fugiat tenetur autem
                deleniti?
              </p>
              <p class="text-sm font-medium py-1 px-2 text-black">
                Tapash paul <span class="text-sm font-normal text-gray-600">/ Front end developer</span>
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

export default {
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
  