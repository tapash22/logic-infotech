<template>
  <div class="scrolling-container">
    <div class="partners-list">
    
      <div v-for="partner in partners" :key="partner.id" class="partner-item">
        <img :src="partner.image" class="partner-image scale-100" />
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
  grid-gap: 10px;
  animation: scrollAnimation 20s linear infinite; 
}

.partner-item {
  width: 100%;
  height: 100%;
  margin-right: 10px; 
}

.partner-image {

  /* animation-delay: -1s;  */
  max-width: 100%;
  max-height: 100%;
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
