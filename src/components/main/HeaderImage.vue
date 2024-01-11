<template>
    <div :class="backgroundImage" class="home-banner">
      <p class="text-5xl font-bold text-white flex justify-center w-full">
       {{title}}
      </p>
    </div>
</template>

<script>
export default {
    props:["title","backgroundImage"]
}
</script>