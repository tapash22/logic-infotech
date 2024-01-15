<template>
  <div class="home -mt-10">
    <HeaderImage title="Contact us"  :backgroundImage="backgroundImage"/>
    <div class="section">
      <ContactBlock :addressLink="addressLink" />
    </div>
    <div class="section contact-form-wrapper">
      <div class="message-section contact-form-block">
        <ContactForm
          :formInput="formInput"
          :formTextarea="formTextarea"
          :buttonClass="buttonClass"
          :title="title"
          :subtitle="subtitle"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ContactForm from "@/components/form/ContactForm";
import ContactBlock from "@/components/card/ContactBlock";
import HeaderImage from "@/components/main/HeaderImage.vue";
import {addressLink} from '../jsonStore/store';

export default {
  data() {
    return {
      backgroundImage:'home-header',
      buttonClass: "form-button1",
      formInput: "form-input-gray",
      formTextarea: "form-textarea-gray",
      mailForm: {
        name: "",
        email: "",
        subject: "",
        message: "",
      },
      addressLink:addressLink,
      title:"LEAVE US MASSAGE",
      subtitle:"How May We Help You!"
    };
  },

  components: {
    ContactForm,
    ContactBlock,
    HeaderImage
  },

  mounted() {
    window.scrollTo(0, 0);
  },

  methods: {
    mailSubmit(e) {
      e.preventDefault();
      console.log(this.mailForm);
    },
  },
};
</script>

<style scoped>
.home-header {
  background-image: url("../assets/images/about.jpg");
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>