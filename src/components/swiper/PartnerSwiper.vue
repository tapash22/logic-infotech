<template>
  <div class="scrolling-container">
    <div class="partners-list">
    
      <div v-for="partner in partners" :key="partner.id" class="partner-item">
        <img :src="partner.image" class="partner-image" />
      </div>
    </div>
  </div>
</template>

<script>
import { partners } from "../../jsonStore/store";

export default {
  data() {
    return {
      partners: partners,
    };
  },
};
</script>

<style scoped>
.scrolling-container {
  overflow: hidden;
  width: 100%;
}

.partners-list {
  display: flex;
  animation: scrollAnimation 20s linear infinite; 
  animation-delay: -10s; 
}

.partner-item {
  margin-right: 10px; 
}

.partner-image {
  max-width: 100%;
  height: auto;
}

@keyframes scrollAnimation {
  0% {
    transform: translateX(100%); 
  }
  100% {
    transform: translateX(-100%); 
  }
}
</style>
