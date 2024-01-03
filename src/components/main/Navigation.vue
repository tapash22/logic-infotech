<template>
    <div class="navbar">
      <!-- <div class="nav-placeholder"></div> -->
      <div
      :class="isFixed ? 'fixed-nav yellow-background' : 'navigation '"
        class="px-16 py-0 flex justify-center w-full shadow-xl shadow-blue-900  z-50"
      >
        <div class="w-1/4 flex justify-start py-2">
          <img src="../../assets/logo/info.png" class="w-28 h-16" />
        </div>
        <ul class="w-3/4 flex justify-end items-center list-none gap-4">
          <li v-for="navL in navLinks" :key="navL.id">
            <router-link
              :to="navL.link"
              class="text-lg font-bold tracking-wide text-white"
            >
              {{ navL.name }}
            </router-link>
          </li>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isFixed: false,
        isYellowBackground: false,
        navLinks: [
          {
            id: 1,
            name: "Home",
            link: "/",
          },
          {
            id: 2,
            name: "About",
            link: "/about",
          },
          {
            id: 3,
            name: "Services",
            link: "/services",
          },
          {
            id: 4,
            name: "Blog",
            link: "/blogs",
          },
          {
            id: 5,
            name: "Contact",
            link: "/contact",
          },
        ],
      };
    },
    methods: {
      handleScroll() {
     
        const scrollPosition = window.scrollY;

          if (scrollPosition > 0) {
            this.isFixed = true;
            this.isYellowBackground = true;
          } else {
            this.isFixed = false;
            this.isYellowBackground = false;
          }
      },
    },
    mounted() {
      window.addEventListener("scroll", this.handleScroll);
    },
    beforeDestroy() {
      window.removeEventListener("scroll", this.handleScroll);
    },
  };
  </script>
  
  <style scoped>
    .fixed-nav {
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.312);
      transition: background-color 0.3s ease;
    }
  
    .yellow-background {
      background-color: rgb(39, 92, 153);
    }
  
    .nav-placeholder {
      height: 20px;
    }
    .navbar{
      background: rgb(18, 18, 143);
    }
  </style>
  