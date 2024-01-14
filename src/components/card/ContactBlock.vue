<template>
    <div class="contact-wrapper">
        <div
          class="contact-wrapper-block"
          v-for="addl in addressLink"
          :key="addl.id"
        >
          <div class="contact-wrapper-block-icon">
            <i
              :class="addl.icon"
              class="contact-wrapper-block-icon-view"
            ></i>
          </div>
          <div class=" contact-wrapper-details">
            <p class="contact-wrapper-details-title">
              {{ addl.title }}
            </p>
            <p
              class="contact-wrapper-details-name"
            >
              {{ addl.name }}
            </p>
          </div>
        </div>
      </div>
</template>

<script>
export default {
    props:['addressLink']
}
</script>