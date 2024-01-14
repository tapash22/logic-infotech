<template>
  <div class="intro-block">
        <div class="intro-block-left">
          <div class="">
            <img
              :src="aboutImage1"
              class="intro-block-left-image"
            />
          </div>
          <div class="">
            <img
              :src="aboutImage2"
              class="intro-block-left-image2"
            />
          </div>
        </div>
      </div>    
</template>

<script>
export default {
    props:["aboutImage1","aboutImage2"]
}
</script>