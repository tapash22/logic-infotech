<template>
  <div class="home -mt-10">
    <div class="home-header home-banner">
      <p class="page-heading">
        Blog
      </p>
    </div>
    <div class="section">
      <BlogCard :blogList="blogList" />
    </div>
  </div>
</template>

<script>
import BlogCard from '@/components/card/BlogCard.vue';

export default {
  data() {
    return {
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
    BlogCard
  },

  mounted() {
    window.scrollTo(0, 0)
  },
};
</script>

<style scoped>
.home-header {
  /* background-image: url("../assets/images/hero2-bg.jpg"); */
  background-image: url("../assets/images/about.jpg");
  /* background-image: url("../assets/images/2.jpg"); */
  /* background-image: url("../assets/images/3.jpg"); */
  background-size: cover;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>