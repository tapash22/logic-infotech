<template>
     <div class="intro-block-wrapper">
        <div
          class="intro-block-wrapper-details"
        >
          <div class="intro-block-wrapper-details-image-first
          ">
            <img
              :src="introImage1"
              class="intro-block-wrapper-details-image-first-view"
            />
          </div>
          <div class="intro-block-wrapper-details-image-second">
            <img
              :src="introImage2"
              class="intro-block-wrapper-details-image-second-view"
            />
          </div>
        </div>
      </div>
</template>

<script>
export default {
    props:["introImage1","introImage2"]
}
</script>