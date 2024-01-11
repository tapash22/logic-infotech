<template>
  <div>
    <span class="section-title user-select-none"> {{title}} </span>
    <p class="section-subtitle user-select-none">
     {{subtitle}}
    </p>
  </div>
</template>

<script>
export default {
    props:['title', 'subtitle']
}
</script>