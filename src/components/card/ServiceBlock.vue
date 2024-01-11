<template>
  <div class="grid grid-cols-4 gap-4 py-5 px-5">
    <div
      v-for="ours in ourServices"
      :key="ours.id"
      class="bg-white py-3 rounded-lg px-4 shadow-lg shadow-gray-500"
    >
      <ServiceCard :ours="ours" />
    </div>
  </div>
</template>
  
  <script>
import ServiceCard from "./ServiceCard.vue";

export default {
  props: ["ourServices"],

  components: {
    ServiceCard,
  },
};
</script>