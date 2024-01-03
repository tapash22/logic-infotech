<template>
  <div class="block">
    <span
      class="footer-info-block-part-title"
      >{{name}}</span
    >
    <ul class="footer-info-block-part-ul" >
      <li
        v-for="exl in listData"
        :key="exl.id"
        class="footer-info-block-part-li-transform"
      >
        <router-link
          :to="exl.link"
          class="text-sm font-medium tracking-wide text-white"
          >{{ exl.name }}</router-link
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["listData","name"],
};
</script>