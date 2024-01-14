<template>
  <div class="navbar">
    <!-- <div class="nav-placeholder"></div> -->
    <div
      :class="isFixed ? 'fixed-nav yellow-background' : 'navigation '"
      class="navigation-wrapper"
    >
      <div class="navigation-image-block">
        <img src="../../assets/logo/logic-info.png" class="navigation-image-block-view" />
      </div>
      <ul class="navigation-block-list">
        <li v-for="navL in navLinks" :key="navL.id">
          <router-link
            :to="navL.link"
            class="navigation-block-list-link"
            :class="{
              'navigation-block-list-link-active': isNavLinkActive(navL.link),
            }"
          >
            {{ navL.name }}
          </router-link>
        </li>
      </ul>
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
.navbar {
  background: rgb(18, 18, 143);
}
</style>
  