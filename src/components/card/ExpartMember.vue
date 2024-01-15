<template>
    <div>
        <img :src="ourT.image" class="team-expart-block-image" />
      <div
        class="team-expart-block-wrapper"
      >
        <div class="team-expart-block-details">
          <p class="team-expart-block-details-name">
            {{ ourT.name }}
          </p>
          <p class="team-expart-block-details-designation">
            {{ ourT.designation }}
          </p>
        </div>

        <ul class="team-expart-block-details-ul">
          <li v-for="social in ourT.social" :key="social">
            <i :class="social" class="team-expart-block-details-ul-icon"></i>
          </li>
        </ul>
      </div>
    </div>
</template>

<script>
export default {
    props:["ourT"]
}
</script>