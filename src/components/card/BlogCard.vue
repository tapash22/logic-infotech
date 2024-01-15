<template>
  <div class="blog-content">
    <div
      v-for="blogL in blogList"
      :key="blogL.id"
      class="relative w-full h-auto group my-10"
    >
      <div class="blog-part-image-block">
        <img :src="blogL.image" class="blog-card-image" />
      </div>
      <div class="blog-date-part">
        <p class="blog-date-part-date">
          {{formatDay(blogL.date) }}
        </p>
        <p class="blog-date-part-month">
          {{ formatMonth(blogL.date)}}
        </p>
      </div>
      <div class="blog-card-details">
        <ul class="blog-card-details-block">
          <li
            class="blog-card-details-block-list"
            v-for="bl in blogL.infoList"
            :key="bl.id"
          >
            <i :class="bl.icon" class="blog-card-details-block-list-icon"></i>
            <span v-if="bl.count" class="blog-card-details-block-list-count">{{
              bl.count
            }}</span>
            <span class="blog-card-details-block-list-name">
              {{ bl.title }}
            </span>
          </li>
        </ul>
        <p class="blog-card-details-block-list-title">
          {{ blogL.title }}
        </p>
        <router-link
          class="blog-card-details-block-list-link"
          :to="{
            name: 'blogdetails',
            params: { id: blogL.id },
            query: { data: JSON.stringify(blogL) },
          }"
        >
          Read More
          <i
            class="fa fa-arrow-right blog-card-details-block-list-link-icon"
          ></i>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["blogList"],

  methods:{
    formatMonth(dateString) {
      const date = new Date(dateString);
      return date.toLocaleDateString(undefined, { month: "short" });
    },
    formatDay(dateString) {
      const date = new Date(dateString);
      return date.toLocaleDateString(undefined, { day: "numeric" });
    },
    formatYear(dateString) {
      const date = new Date(dateString);
      return date.toLocaleDateString(undefined, { year: "numeric" });
    },
  }
};
</script>
