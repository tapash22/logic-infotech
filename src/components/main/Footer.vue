<template>
  <div class="footer-cover footer-wrapper relative">
    <!-- subscribe box -->
    <div class="footer-subscribe">
      <form class="box footer-subscribe-form">
        <p class="footer-subscribe-text">Subscribe to our newsletter</p>
        <input
          type="text"
          class="footer-subscribe-input"
          placeholder="Enter Your Email"
        />
        <button class="footer-subscribe-button">Subscribe</button>
      </form>
    </div>
    <!-- subscribe box end -->

    <!-- footer information -->
    <div class="footer-info footer-cover">
      <div class="footer-info-block">
        <div class="footer-info-block-logo-block">
          <img
            src="../../assets/logo/logic-info.png"
            class="footer-info-block-logo-block-logo"
          />
          <p class="footer-info-block-logo-block-text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint
            corporis nisi explicabo maiores sunt at similique rerum, quas
            exercitationem vitae, minima laudantium. Labore quas accusantium
            aspernatur placeat delectus eaque animi.
          </p>
        </div>
        <div class="footer-info-block-part">
          <FooterList :listData="extraLink" name="Useful Links" />
        </div>
        <div class="footer-info-block-part">
          <FooterList :listData="extraServices" name="Our Services" />
        </div>
        <div class="footer-info-block-part">
          <FooterInfo
            name="Contact Information"
            :infoDetails="addressLink"
            :socialLinks="socialLinks"
          />
        </div>
      </div>
    </div>
    <!-- footer information end -->

    <!-- footer bottom -->
    <div class="flex justify-center py-2 ring-1 ring-white">
      <p class="text-sm font-normal text-gray-300">
        All Right Reserved Logic Software Ltd.
      </p>
    </div>
    <!-- footer bottom end -->
  </div>
</template>

<script>
import FooterList from "@/components/footerpart/FooterList";
import FooterInfo from "@/components/footerpart/FooterInfo";
import {
  socialLinks,
  addressLink1,
  extraServices,
  extraLink,
} from "../../jsonStore/store";

export default {
  data() {
    return {
      extraLink: extraLink,
      extraServices: extraServices,
      addressLink: addressLink1,
      socialLinks: socialLinks,
    };
  },
  components: {
    FooterList,
    FooterInfo,
  },
};
</script>

<style scoped>
.footer-cover {
  background-image: url("../../assets/images/1.jpg");
  background-position: center;
  background-size: cover;
  object-fit: cover;
}

.box {
  background: rgb(27, 27, 124);
  box-shadow: 0px 5px 10px rgb(112, 79, 194);
  margin-top: -60px;
}
</style>