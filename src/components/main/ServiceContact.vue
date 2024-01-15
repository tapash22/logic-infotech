<template>
     <div class="service-contact-wrapper-block">
          <div class="service-contact-wrapper-title-block">
            <h1
              class="user-select-none service-contact-wrapper-title-block-view"
            >
              {{ tag }}
            </h1>
          </div>
          <div class="service-contact-wrapper-block-details">
            <div class="service-contact-wrapper-block-details-image-block">
              <img src="../../assets/services/icon.png" class="service-contact-wrapper-block-details-image-block-view" />
            </div>
            <span
              class="service-contact-wrapper-block-details-text"
            >
             {{ title }}
            </span>
            <p class="service-contact-wrapper-block-details-contact">
              {{contact}}
            </p>
          </div>
        </div>
</template>

<script>
export default {
    props:["tag","title","contact"]
}
</script>