<template>
  <div>
    <span class="section-title user-select-none" :style="expartStyle"> {{title}} </span>
    <p class="section-subtitle user-select-none" :style="expartStyle">
     {{subtitle}}
    </p>
  </div>
</template>

<script>
export default {
    props:['title', 'subtitle',"expartStyle"]
}
</script>