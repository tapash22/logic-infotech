<template>
  <div class="home block">
    <!-- <div class="block w-full h-auto px-5 py-3">
      <span class="text-sm font-normal tracking-wide flex justify-center">
        WHAT WE PROVIDE
      </span>
      <p class="text-xl font-bold tracking-wide py-2 flex justify-center">
        We provide truly prominent Software solutions.
      </p>
      <div
        class="py-1 w-full h-auto flex justify-center px-5 bg-yellow-500"
      ></div>
    </div> -->

    <!-- contact block -->
    <div class="flex w-full h-auto px-5 py-10">
      <!-- left side -->
      <div class="w-1/2 h-auto block">
        <h1
          class="font-bold tracking-wide flex justify-start px-2 text-3xl border-l-4 border-indigo-500 mr-36 mb-5"
        >
          To make requests for further information, contact us
        </h1>
        <div
          class="flex w-full my-2 py-2 px-2"
          v-for="info in information"
          :key="info.id"
        >
          <div class="w-1/4 h-auto flex justify-center items-center">
            {{ info.icon }}
          </div>
          <div class="w-2/4 block px-1">
            <h3
              class="font-bold tracking-wide flex justify-start text-2xl"
            >
              {{ info.property }}
            </h3>
            <p class="break-all text-sm font-medium text-black mr-16">
              {{ info.value }}
            </p>
          </div>
        </div>
      </div>
      <!-- left side end -->

      <!-- right side -->
      <div
        class="w-1/2 h-auto bg-gray-300 py-4 flex justify-center items-center rounded-lg"
      >
        <form class="w-full px-5 py-2 block">
          <span
            class="text-sm uppercase font-normal tracking-wider flex justify-center"
            >LEAVE US MASSAGE</span
          >
          <h1 class="font-bold tracking-wide flex justify-center text-2xl">
            How May We Help You!
          </h1>
          <div class="block">
            <label class="w-full py-2 text-sm font-medium tracking-wide"
              >Name</label
            >
            <input
              type="text"
              class="h-10 w-full bg-white rounded-lg py-2 px-2 text-sm font-bold tracking-wide"
              placeholder="Full Name"
            />
          </div>
          <div class="block">
            <label class="w-full py-2 text-sm font-bold tracking-wide"
              >Email</label
            >
            <input
              type="text"
              class="h-10 w-full bg-white rounded-lg py-2 px-2 text-sm font-bold tracking-wide"
              placeholder="Email"
            />
          </div>
          <div class="block">
            <label class="w-full py-2 text-sm font-bold tracking-wide"
              >Subject</label
            >
            <input
              type="text"
              class="h-10 w-full bg-white rounded-lg py-2 px-2 text-sm font-bold tracking-wide"
              placeholder="Subject"
            />
          </div>
          <div class="block">
            <label class="w-full py-2 text-sm font-bold tracking-wide"
              >Name</label
            >
            <textarea
              class="w-full py-2 px-2 text-sm font-bold tracking-wide h-auto"
              placeholder="Write A Message"
            >
            </textarea>
          </div>
          <div class="w-full py-2 block">
            <button
              class="text-sm font-bold bg-gray-600 text-white w-full py-3 rounded-lg"
            >
              Send Message
            </button>
          </div>
        </form>
      </div>
      <!-- right side end -->
    </div>

    <!-- contact block end -->
  </div>
</template>

<script>
export default {
  name: "Home",

  data() {
    return {
      information: [
        {
          id: 1,
          property: "Contact Number",
          value: "+00(1) 123 456 7890",
          icon: "",
        },
        {
          id: 2,
          property: "Our Mail",
          value: "infotechmax@ourmail.com",
          icon: "",
        },
        {
          id: 3,
          property: "Our Location",
          value:
            "New ipsum dolor amet, eiusmod adipisicing 147 New Yors, NY Adipisicing 123",
          icon: "",
        },
      ],
    };
  },
  components: {},
};
</script>

<style scoped>
input:focus,
textarea:focus {
  outline: none;
}

input::placeholder,
textarea::placeholder {
  font-size: 12px;
  font-weight: 500;
  color: gray;
  letter-spacing: 1px;
}
</style>
