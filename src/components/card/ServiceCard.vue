<template>
  <div>
    <div class="product-icon-block py-3">
      <img :src="ours.image" />
    </div>
    <p class="product-type">
      {{ ours.title }}
    </p>
    <p class="product-details leading-7">
      {{ ours.details }}
    </p>
    <div class="flex justify-start px-2 py-2">
      <button
        class="px-4 py-2 rounded-lg text-sm font-bold tracking-wide text-white bg-indigo-950 opacity-80 hover:opacity-100 transition-all delay-150"
      >
        View
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["ours"],
};
</script>