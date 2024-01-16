<!-- VideoPlayer.vue -->
<template>
    <div>
      <iframe
        
        class="iframe"
        :src="videoUrl"
        frameborder="0"
        allowfullscreen
      ></iframe>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      videoUrl: {
        type: String,
        required: true,
      },
    },
  };
  </script>

  