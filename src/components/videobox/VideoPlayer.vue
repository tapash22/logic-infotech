<!-- VideoPlayer.vue -->
<template>
    <div>
      <iframe
        width="560"
        height="315"
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
  
  <style scoped>
  /* Add your component styles here */
  </style>
  