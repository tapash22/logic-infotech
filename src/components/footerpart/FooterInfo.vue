<template>
  <div class="block">
    <span
      class="footer-info-block-part-title"
      >Contact Information</span
    >
    <ul class="footer-info-block-part-ul">
      <li
        v-for="addl in infoDetails"
        :key="addl.id"
        class="footer-info-block-part-li"
      >
        {{ addl.name }}
      </li>
    </ul>
    <ul class="footer-info-block-part-social">
      <li v-for="social in socialLinks" :key="social.id">
        <a :href="social.link" target="_blank"
          ><i
            :class="social.icon"
            class="footer-info-block-part-social-icon"
          ></i
        ></a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["infoDetails", "socialLinks", "name"],
};
</script>