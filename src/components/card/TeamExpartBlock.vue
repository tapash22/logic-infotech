<template>
  <div class="team-expart-block">
    <div
      v-for="ourT in ourTeams"
      :key="ourT.id"
      class="team-expart-block-view relative group "
    >
     <ExpartMember :ourT="ourT" />
    </div>
  </div>
</template>

<script>
import ExpartMember from './ExpartMember.vue';

export default {
  props: ["ourTeams"],

  components:{
    ExpartMember
  }
};
</script>