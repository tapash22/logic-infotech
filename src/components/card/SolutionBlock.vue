<template>
  <div class="intro-block-product">
    <div
      v-for="ours in ourSolution"
      :key="ours.id"
      class="intro-block-product-card"
    >
      <SingleSolution :ours="ours" @openBox="openBox" />
    </div>
  </div>
</template>

<script>
import SingleSolution from "./SingleSolution.vue";

export default {
  props: ["ourSolution"],

  data() {
    return {
      solutionData: {},
    };
  },

  methods: {
    openBox(data) {
      this.solutionData = data;
      this.$emit("solutionView", this.solutionData);
    },
  },

  components: {
    SingleSolution,
  },
};
</script>