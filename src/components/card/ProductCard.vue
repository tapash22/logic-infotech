<template>
  <div class="product-view">
    <div
      class="product-card product-card-view"
      v-for="cardv in cardView"
      :key="cardv.id"
    >
      <div class="product-icon-block">
        <i class="icon-card product-icon" :class="cardv.icon"> </i>
      </div>
      <p class="product-type">
        {{ cardv.name }}
      </p>
      <p class="product-details">
        {{ cardv.text }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["cardView"],
};
</script>

<style scoped>
.product-card i {
  transition: transform 0.3s ease-in-out;
}
.product-card:hover i {
  transform: translateX(100%);
}
</style>