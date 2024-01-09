<template>
  <div class="home -mt-10">
    <div class="home-header home-banner">
      <p class="text-5xl font-bold text-white flex justify-center w-full">
        Contact us
      </p>
    </div>
    <div class="section">
      <div class="grid grid-cols-3 gap-5 py-2 px-5">
        <div
          class="block px-3 py-3 bg-gray-200 rounded-lg"
          v-for="addl in addressLink"
          :key="addl.id"
        >
          <div class="flex justify-center py-1">
            <i
              :class="addl.icon"
              class="text-5xl font-bold text-indigo-950"
            ></i>
          </div>
          <div class="block py-2 px-2">
            <p class="text-2xl font-bold flex justify-center py-2">
              {{ addl.title }}
            </p>
            <p
              class="text-lg font-semibold flex justify-center tracking-wide py-2"
            >
              {{ addl.name }}
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="section flex justify-center items-center">
      <div class="message-section bg-white shadow-lg shadow-gray-300">
        <form class="submit-form" @submit="mailSubmit">
          <span class="form-title">LEAVE US MASSAGE</span>
          <h1 class="form-subtitle">How May We Help You!</h1>
          <div class="block">
            <label class="form-label">Name</label>
            <input
              type="text"
              v-model="mailForm.name"
              class="form-input ring-1 ring-gray-300"
              placeholder="Full Name"
            />
          </div>
          <div class="block">
            <label class="form-label">Email</label>
            <input
              type="text"
              v-model="mailForm.email"
              class="form-input ring-1 ring-gray-300"
              placeholder="Email"
            />
          </div>
          <div class="block">
            <label class="form-label">Subject</label>
            <input
              type="text"
              v-model="mailForm.subject"
              class="form-input ring-1 ring-gray-300"
              placeholder="Subject"
            />
          </div>
          <div class="block">
            <label class="form-label">Message</label>
            <textarea
              v-model="mailForm.message"
              class="form-textarea ring-1 ring-gray-300"
              placeholder="Write A Message"
            >
            </textarea>
          </div>
          <div class="w-full py-2 block">
            <button class="form-button bg-indigo-700" type="submit">Send Message</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
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

  mounted(){
        window.scrollTo(0,0)
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