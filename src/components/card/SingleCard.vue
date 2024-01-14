<template>
  <div class="single-card-wrapper relative group">
    <div class="single-card-image-block">
        <img :src="pc.image" class="single-card-image-block-view" />
    </div>
    <div
      class="single-card-details"
    >
      <router-link
        :to="pc.link"
        class="single-card-details-link"
      >
        {{ pc.name }}
      </router-link>
      <p class="single-card-details-text">
        {{ pc.message }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["pc"],
};
</script>