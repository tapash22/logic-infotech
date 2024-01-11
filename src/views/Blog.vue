<template>
  <div class="home -mt-10">
    <HeaderImage title="Blog"  :backgroundImage="backgroundImage"/>
    <div class="section">
      <BlogCard :blogList="blogList" />
    </div>
  </div>
</template>

<script>
import BlogCard from '@/components/card/BlogCard.vue';
import HeaderImage from '@/components/main/HeaderImage.vue';

export default {
  data() {
    return {
      backgroundImage:'home-header',
      blogList: [
        {
          id: 1,
          title: "How to become a successful businessman",
          image: require("../assets/blog/1.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 8,
            },
          ],
        },
        {
          id: 2,
          title: "Who Needs Extract Value From Data?",
          image: require("../assets/blog/2.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 5,
            },
          ],
        },
        {
          id: 3,
          title: "Easy and Most Powerful Server and Platform.",
          image: require("../assets/blog/3.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 10,
            },
          ],
        },
        {
          id: 4,
          title: "How to become a successful businessman",
          image: require("../assets/blog/1.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 8,
            },
          ],
        },
        {
          id: 5,
          title: "Who Needs Extract Value From Data?",
          image: require("../assets/blog/2.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 5,
            },
          ],
        },
        {
          id: 6,
          title: "Easy and Most Powerful Server and Platform.",
          image: require("../assets/blog/3.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 10,
            },
          ],
        },
        {
          id: 7,
          title: "Easy and Most Powerful Server and Platform.",
          image: require("../assets/blog/3.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 10,
            },
          ],
        },
        {
          id: 8,
          title: "How to become a successful businessman",
          image: require("../assets/blog/1.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 8,
            },
          ],
        },
        {
          id: 9,
          title: "Who Needs Extract Value From Data?",
          image: require("../assets/blog/2.jpg"),
          day: 10,
          month: "Aug",
          infoList: [
            {
              id: 1,
              icon: "fa fa-user",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "fa fa-comments-o",
              title: "Comments",
              count: 5,
            },
          ],
        },

      ],
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