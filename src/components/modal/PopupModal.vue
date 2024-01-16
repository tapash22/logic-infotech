<template>
    <div
        class="popup-wrapper"
      >
        <div
          class="popup-wrapper-block"
        >
          <div class="product-icon-block popup-wrapper-block-image">
            <img :src="popupview.image" />
          </div>
          <p class="product-type">
            {{ popupview.title }}
          </p>
          <p class="product-details leading-7">
            {{ popupview.details }}
          </p>
          <p class="popup-wrapper-block-text">
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Optio,
            quam autem facilis sunt mollitia accusamus facere laboriosam quos.
            Aperiam voluptate maxime minus, et aut magnam expedita qui. Tempore,
            cupiditate atque!
          </p>
          <router-link to="/contact" class="popup-wrapper-block-link">
            <span class="popup-wrapper-block-link-text">Contact with us</span> 
          </router-link>
          <div class=" block">
            <ul class="popup-wrapper-block-social-block-ul">
              <li v-for="sl in socialLinks" :key="sl.id" class="popup-wrapper-block-social-block-li">
                <a :href="sl.link" class="no-underline">
                  <i :class="sl.icon" class="popup-wrapper-block-social-block-li-icon"></i>
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div class="popup-wrapper-block-close" >
          <i class="fa fa-times " @click="closeView"></i>
        </div>
      </div>
</template>

<script>
export default {
    props:["popupview","socialLinks"],

    methods:{
        closeView(){
            this.$emit("closeView")
        }
    }
}
</script>