<template>
  <div id="app">
    <Navigation />
    <div class="main">
      <router-view />
    </div>
    <Footer />
  </div>
</template>

<script>
import Navigation from "@/components/main/Navigation";
import Footer from "@/components/main/Footer";

export default {
  data() {
    return {};
  },

  components: {
    Navigation,
    Footer,
  },
};
</script>

<style scoped>
.main{
  width: 100%;
  height: auto;
  padding: 0;
  margin: 0;
  /* background: white; */
}
</style>
