<template>
    <div :class="backgroundImage" class="home-banner">
      <p class="home-banner-title">
       {{title}}
      </p>
    </div>
</template>

<script>
export default {
    props:["title","backgroundImage"]
}
</script>