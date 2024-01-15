<template>
  <div class="home -mt-10">
    <HeaderImage title="Blog"  :backgroundImage="backgroundImage"/>
    <div class="section px-5">
      <BlogCard :blogList="blogList" />
    </div>
  </div>
</template>

<script>
import BlogCard from '@/components/card/BlogCard.vue';
import HeaderImage from '@/components/main/HeaderImage.vue';
import {blogList} from '../jsonStore/store';

export default {
  data() {
    return {
      backgroundImage:'home-header',
      blogList: blogList
    };
  },

  components: {
    BlogCard,
    HeaderImage
  },

  mounted() {
    window.scrollTo(0, 0)
  },
};
</script>

<style scoped>
.home-header {
  background-image: url("../assets/images/about.jpg");
  background-size: cover;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>