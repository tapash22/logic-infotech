<template>
  <div id="app">
    <Navigation />
      <router-view />
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
#app{
  display: block;
  width: 100%;
  height: 100%;
  /* background: red; */
}
</style>
