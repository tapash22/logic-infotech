<template>
  <div>
    <div class="product-icon-block py-3">
      <img :src="ours.image" />
    </div>
    <p class="product-type">
      {{ ours.title }}
    </p>
    <p class="product-details leading-7">
      {{ ours.details }}
    </p>
    <div class="product-button-block">
      <button
      @click="showBox"
        class="product-button-block-view"
      >
        View
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["ours"],

  methods:{
    showBox() {
      this.$emit('openBox',this.ours); 
    }
  }
};
</script>