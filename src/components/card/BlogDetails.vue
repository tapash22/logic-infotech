<template>
  <div class="home">
    <div class="section  px-5 py-4">

      <span class="section-title user-select-none underline underline-offset-8 "> Blog Details </span>
      <p class="section-subtitle user-select-none">
        {{blog.title}}
      </p>
      <div class="px-3 py-2 flex justify-between">
       <div class="flex justify-center items-center px-2 w-1/3 ">
        <img :src="blog.image" class="" />
       </div>
       <div class="block px-2 py-2 w-2/3 h-auto ">
       <p class="text-sm font-bold ">
      <span class="text-lg font-bold tracking-wide px-1">Publish Date: </span>  {{ new Date().toISOString() }}
       </p>
       <p class="text-lg font-normal tracking-wide text-justify py-2">
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