<template>
  <div class="navbar">
    <div
      :class="isFixed ? 'fixed-nav yellow-background' : 'navigation '"
      class="navigation-wrapper"
    >
      <div class="navigation-image-block">
        <router-link to="/">
          <img
            src="../../assets/logo/logic-info.png"
            class="navigation-image-block-view"
        /></router-link>

        <button
        @click="toggleMenu"
        class="sm:hidden block absolute top-0 right-0 mt-4 mr-6 focus:outline-none"
      >
        <svg
          class="w-6 h-6 text-white"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16m-7 6h7"
          ></path>
        </svg>
      </button>
      </div>
      <ul v-if="!isMobile"  class="navigation-block-list hidden sm:flex">
        <li v-for="navL in navLinks" :key="navL.id">
          <router-link
            :to="navL.link"
            class="navigation-block-list-link text-white"
            :class="{
              'navigation-block-list-link-active': isNavLinkActive(navL.link),
            }"
          >
            {{ navL.name }}
          </router-link>
        </li>
      </ul>

      <transition name="slide-fade">
        <div v-if="isMobile && isMenuOpen" class="mobile-menu-card">
          <ul class="mobile-menu-list">
            <li v-for="navL in navLinks" :key="navL.id">
              <router-link
                :to="navL.link"
                class="mobile-menu-list-link text-white"
                :class="{
                  'mobile-menu-list-link-active': isNavLinkActive(navL.link),
                }"
              >
                {{ navL.name }}
              </router-link>
            </li>
          </ul>
        </div>
      </transition>
    </div>
  </div>
</template>
  
  <script>
import { navLinks } from "../../jsonStore/store";

export default {
  data() {
    return {
      isFixed: false,
      isYellowBackground: false,
      isMobile: false,
      isMenuOpen: false,
      navLinks: navLinks,
    };
  },

  watch: {
    $route(to) {
      this.currentRoute = to.path;
    },
  },

  methods: {
    isNavLinkActive(link) {
      return this.$route.path === link;
    },
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

    toggleMenu(){
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
    },
    checkMobile() {
      this.isMobile = window.innerWidth <= 640; 
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
    window.addEventListener("resize", this.checkMobile);
    this.checkMobile();
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
    window.removeEventListener("resize", this.checkMobile);
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
.navbar {
  background: rgb(18, 18, 143);
}

.mobile-menu-card {
  position: absolute;
  top: 70px; /* Adjust based on your header height */
  right: 0;
  width: 100%;
  background-color: rgb(18, 18, 143);
  z-index: 999;
  border-radius: 4px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  overflow: hidden;
}

.mobile-menu-list {
  padding: 0;
  list-style: none;
  margin: 0;
}

.mobile-menu-list-link {
  display: block;
  padding: 12px;
  text-decoration: none;
  color: white;
  transition: background-color 0.3s ease;
}

.mobile-menu-list-link:hover {
  background-color: rgba(255, 255, 255, 0.1);
}

/* Transition for the card appearance */
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: opacity 0.3s, transform 0.3s;
}

.slide-fade-enter,
.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
  