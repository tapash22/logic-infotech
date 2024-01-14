<!-- VideoPlayer.vue -->
<template>
    <div>
      <iframe
        width="800"
        height="400"
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

  