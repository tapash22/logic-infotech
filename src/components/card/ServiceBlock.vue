<template>
  <div class="grid grid-cols-4 gap-4 py-5 px-5 overflow-hidden">
    <div
      v-for="ours in ourServices"
      :key="ours.id"
      class="bg-white py-3 rounded-lg px-4 shadow-lg shadow-gray-500"
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