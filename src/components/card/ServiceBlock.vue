<template>
  <div class="service-wrapper">
    <div
      v-for="ours in ourServices"
      :key="ours.id"
      class="service-wrapper-block"
    >
      <ServiceCard :ours="ours" @openBox="openBox" />
    </div>
  </div>
</template>
  
  <script>
import ServiceCard from "./ServiceCard.vue";

export default {
  props: ["ourServices"],

  data() {
    return {
      serviceData: {},
    };
  },

  methods: {
    openBox(data) {
      this.serviceData = data;
      this.$emit("serviceView",this.serviceData);
    },

    // closeModel() {
    //   this.show = falsa;
    // },
  },

  components: {
    ServiceCard,
  },
};
</script>