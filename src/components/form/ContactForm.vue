<template>
  <form class="submit-form" @submit="mailSubmit">
    <span class="form-title">{{ title }}</span>
    <h1 class="form-subtitle">{{ subtitle }}</h1>
    <div class="block">
      <label class="form-label">Name</label>
      <input
        type="text"
        v-model="mailForm.name"
        :class="formInput"
        placeholder="Full Name"
      />
    </div>
    <div class="block">
      <label class="form-label">Email</label>
      <input
        type="text"
        v-model="mailForm.email"
        :class="formInput"
        placeholder="Email"
      />
    </div>
    <div class="block">
      <label class="form-label">Subject</label>
      <input
        type="text"
        v-model="mailForm.subject"
        :class="formInput"
        placeholder="Subject"
      />
    </div>
    <div class="block">
      <label class="form-label">Message</label>
      <textarea
        v-model="mailForm.message"
        :class="formTextarea"
        placeholder="Write A Message"
      >
      </textarea>
    </div>
    <div class="w-full py-2 block">
      <button :class="buttonClass" type="submit">Send Message</button>
    </div>
  </form>
</template>

<script>
export default {
  props: ["formInput","formTextarea","buttonClass", "title", "subtitle"],
  data() {
    return {
      mailForm: {
        name: "",
        email: "",
        subject: "",
        message: "",
      },
    };
  },
  methods: {
    mailSubmit(e) {
      e.preventDefault();
      console.log(this.mailForm);
    },
  },
};
</script>