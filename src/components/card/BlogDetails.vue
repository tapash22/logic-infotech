<template>
  <div class="home">
    <div class="section blog-details-wrapper">

      <span class=" section-title blog-details-wrapper-title user-select-none"> Blog Details </span>
      <p class="section-subtitle user-select-none">
        {{blog.title}}
      </p>
      <div class="blog-details-wrapper-block">
       <div class="blog-details-wrapper-block-image">
        <img :src="blog.image" class="" />
       </div>
       <div class="blog-details-wrapper-info-block">
       <p class=".blog-details-wrapper-info-block-publish">
      <span class="blog-details-wrapper-info-block-publish-view">Publish Date: </span>  {{ new Date().toISOString() }}
       </p>
       <p class="blog-details-wrapper-info-block-publish-text">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ullam reprehenderit quasi asperiores corporis quia dolorem numquam nisi fugiat esse laborum amet architecto nobis suscipit molestias, aspernatur laudantium quisquam distinctio assumenda!
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam maxime, doloremque repudiandae ex nihil ipsam assumenda asperiores? Laudantium incidunt excepturi in voluptatum nobis vitae optio, aliquid et numquam possimus assumenda?
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsum ut delectus unde facilis officiis, quisquam, reiciendis laudantium consectetur saepe aspernatur praesentium! Rem quas sit beatae adipisci repellat in dolor architecto?
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis, incidunt nobis similique, mollitia harum optio odio placeat nam, temporibus quis expedita ipsam aliquid neque officia iusto? Cumque expedita nemo deleniti?
       </p>

       </div>
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blogId: null,
      blog: {
        id: null,
        title: null,
        image: null,
        infoList: [],
      },
    };
  },
  mounted() {
    window.scrollTo(0, 0);
    const blogId = this.$route.params.id;
    console.log(blogId);
    const storedBlog = this.$route.query.data;

    if (storedBlog) {
      this.blog = JSON.parse(storedBlog);
    } else {
      this.fetchProductDetails(blogId);
    }
  },

  methods: {
    fetchProductDetails(blogId) {
      console.log(blogId);
    },
  },
};
</script>