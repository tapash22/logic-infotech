<template>
  <div class="home -mt-10">
    <HeaderImage title="Contact us"  :backgroundImage="backgroundImage"/>
    <!-- <div class="home-header home-banner">
      <p class="text-5xl font-bold text-white flex justify-center w-full">
        Contact us
      </p>
    </div> -->
    <div class="section">
      <ContactBlock :addressLink="addressLink" />
    </div>
    <div class="section flex justify-center items-center">
      <div class="message-section bg-white shadow-lg shadow-gray-300">
        <ContactForm
          :formInput="formInput"
          :formTextarea="formTextarea"
          :buttonClass="buttonClass"
          title="LEAVE US MASSAGE"
          subtitle="How May We Help You!"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ContactForm from "@/components/form/ContactForm";
import ContactBlock from "@/components/card/ContactBlock";
import HeaderImage from "@/components/main/HeaderImage.vue";

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

      addressLink: [
        {
          id: 1,
          title: "Give us a call",
          name: "+8801600000000",
          icon: "fa fa-phone",
        },
        {
          id: 2,
          title: "Drop us a line",
          name: "info@logicinfotech.com",
          icon: "fa fa-envelope-o",
        },
        {
          id: 3,
          title: "Visit our office",
          name: "House:85, Road:04, Banani, Dhaka",
          icon: "fa fa-map-marker",
        },
      ],
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
  /* background-image: url("../assets/images/hero2-bg.jpg"); */
  background-image: url("../assets/images/about.jpg");
  /* background-image: url("../assets/images/2.jpg"); */
  /* background-image: url("../assets/images/3.jpg"); */
  background-size: cover;
  height: 100vh;
  object-fit: cover;
  margin-bottom: 50px;
}
</style>