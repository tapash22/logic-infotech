<template>
  <div class="home -mt-10">
    <div class="home-header home-banner">
      <p class="text-5xl font-bold text-white flex justify-center w-full">
        Blog
      </p>
    </div>
    <div class="section">
      <div class="grid grid-cols-3 gap-5 py-2 px-5">
        <div
          v-for="blogL in blogList"
          :key="blogL.id"
          class="relative w-full h-auto group overflow-hidden"
        >
          <img
            :src="blogL.image"
            class="w-full h-full scale-100 hover:scale-110 transition-all delay-100 rounded-lg"
          />
          <div
            class="absolute top-4 left-4 bg-indigo-950 opacity-85 block px-4 py-2 rounded-lg"
          >
            <p class="text-xl font-bold flex justify-center text-white">
              {{ blogL.day }}
            </p>
            <p class="text-xl font-medium flex justify-center text-white">
              {{ blogL.month }}
            </p>
          </div>

          <div
            class="absolute bottom-2 left-2 right-2 bg-white block px-4 py-2"
          >
          <ul class="flex justify-center gap-3 list-none">
            <li class="flex justify-between" v-for="bl in blogL.infoList" :key="bl.id">
                <i :class="bl.icon" class="text-sm font-bold text-indigo-950 "></i>
                <span v-if="bl.count" class="text-sm font-normal">{{ bl.count }}</span>
                <span class="text-sm font-normal text-black">
                    {{ bl.title }}
                </span>
            </li>
          </ul>
          <p class="text-lg font-semibold py-2 px-2 text-indigo-900">
            Read More <i class="font-medium text-lg text-indigo-950"></i>
          </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blogList: [
        {
          id: 1,
          title: "",
          image: require("../assets/blog/1.jpg"),
          day: 10,
          month: "Aug",
          title: "How to become a successful businessman",
          infoList: [
            {
              id: 1,
              icon: "",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "",
              title: "Comments",
              count: 10,
            },
          ],
        },
        {
          id: 2,
          title: "",
          image: require("../assets/blog/2.jpg"),
          day: 10,
          month: "Aug",
          title: "Who Needs Extract Value From Data?",
          infoList: [
            {
              id: 1,
              icon: "",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "",
              title: "Comments",
              count: 10,
            },
          ],
        },
        {
          id: 3,
          title: "",
          image: require("../assets/blog/3.jpg"),
          day: 10,
          month: "Aug",
          title: "Easy and Most Powerful Server and Platform.",
          infoList: [
            {
              id: 1,
              icon: "",
              title: "Andrew Paker",
            },
            {
              id: 2,
              icon: "",
              title: "Comments",
              count: 10,
            },
          ],
        },
      ],
    };
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