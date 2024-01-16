<template>
    <div class="home-contact-wrapper">
        <h1
          class="home-contact-wrapper-title user-select-none"
        >
          To make requests for further information, contact us
        </h1>
        <div
          class="home-contact-wrapper-block"
          v-for="info in information"
          :key="info.id"
        >
          <div class="home-contact-wrapper-block-icon">
            <i
              :class="info.icon"
              class="home-contact-wrapper-block-icon-view"
            ></i>
          </div>
          <div class="home-contact-wrapper-block-details">
            <h3 class="home-contact-wrapper-block-details-property">
              {{ info.property }}
            </h3>
            <p class="home-contact-wrapper-block-details-value">
              {{ info.value }}
            </p>
          </div>
        </div>
      </div>
</template>

<script>
export default {
    props:["title","information"]
}
</script>