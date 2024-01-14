<template>
  <div class="home-header home-banner">
    <div class="banner-block">
      <span class="home-banner-title user-select-none">
        {{ title }}
      </span>
      <p class="home-banner-subtitle user-select-none">
        {{subtitle}}
      </p>
      <div class="home-banner-icon-section">
        <div class="home-banner-icon-block" @click="showView">
          <i class="fa fa-play home-banner-icon" aria-hidden="true"></i>
        </div>
        <p class="home-banner-icon-text user-select-none">{{button}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "subtitle", "button"],
};
</script>

<style scoped>
.home-header {
  background-image: url("../../assets//images//1.jpg");
  background-size: cover;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>