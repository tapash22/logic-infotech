<template>
  <div class="intro-block-right">
    <span class="intro-block-right-title">
      {{ title }}
    </span>
    <p class="intro-block-right-subtitle">
      {{ subtitle }}
    </p>
    <p class="intro-block-right-text">
      {{ introText }}
    </p>

    <div
      class="px-3 py-5 bg-gray-300 rounded-lg flex justify-center my-4"
      v-if="introBox"
    >
      <i
        :class="introBox.icon"
        class="text-3xl font-bold text-indigo-950 px-2 flex items-center"
        aria-hidden="true"
      ></i>
      <p
        class="text-lg font-bold px-2 tracking-wide text-center text-indigo-950"
      >
        {{ introBox.details }}
      </p>
    </div>

    <!-- last part -->
    <div class="intro-block-bottom">
      <div
        class="intro-block-bottom-card"
        v-for="intro in introduce"
        :key="intro.id"
      >
        <div class="intro-block-bottom-card-first">
          <i
            v-if="intro.icon"
            :class="intro.icon"
            class="intro-block-bottom-card-first-icon"
            aria-hidden="true"
          ></i>
          <span class="intro-block-bottom-card-first-title">
            {{ intro.name }}
          </span>
        </div>
        <p class="intro-block-bottom-card-first-details">
          {{ intro.details }}
        </p>
      </div>
    </div>
    <!-- last part end -->
  </div>
</template>

<script>
export default {
  props: ["title", "subtitle", "introText", "introBox", "introduce"],
};
</script>