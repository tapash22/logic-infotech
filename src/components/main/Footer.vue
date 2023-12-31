<template>
  <div class="block w-full footer-cover relative">
    <div class="w-full h-auto px-6 py-5 flex justify-center " >
    <form class="flex justify-center py-3 px-4  bg-yellow-500 w-1/2 rounded-lg items-center" style="margin-top:-80px ">
        <p class="text-lg font-bold py-1 w-1/3 ">
            Subscribe to us
        </p>
        <input type="text" class="h-10 rounded-bl-lg rounded-tl-lg py-2 px-3 w-full bg-white ring-1 ring-white" />
        <button class="bg-black h-10 rounded-tr-lg rounded-br-lg text-white text-sm font-bold px-2">Subscribe</button>
    </form>
    </div>
    <div class="px-10 py-2 flex justify-center w-full footer-cover">
      <div class="w-full h-auto px-3 py-3 flex justify-start">
        <!-- 1st part -->
        <div class="block px-2 w-1/4 h-auto">
          <img
            src="../../assets/logo.png"
            class="w-24 h-14 flex justify-center px-2"
          />
          <p class="font-medium text-sm text-white tracking-wide text-justify mr-7">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint
            corporis nisi explicabo maiores sunt at similique rerum, quas
            exercitationem vitae, minima laudantium. Labore quas accusantium
            aspernatur placeat delectus eaque animi.
          </p>
        </div>
        <!-- 1st part end -->
        <!-- 2st part -->
        <div class="flex justify-center px-2 w-1/4 h-auto">
          <div class="block">
            <span class="text-lg font-bold tracking-wide py-2 text-white"
              >Useful Links</span
            >
            <ul class="list-none p-0 m-0 block py-3">
              <li
                v-for="exl in extraLink"
                :key="exl.id"
                class="py-1 translate-x-0 hover:translate-x-2 transition-all delay-100"
              >
                <router-link
                  :to="exl.link"
                  class="text-sm font-medium tracking-wide text-white"
                  >{{ exl.name }}</router-link
                >
              </li>
            </ul>
          </div>
        </div>
        <!-- 2st part end -->

        <!-- 3rd part -->
        <div class="flex justify-center px-2 w-1/4 h-auto">
          <div class="block">
            <span class="text-lg font-bold tracking-wide py-2 text-white"
              >Our Services</span
            >

            <ul class="list-none p-0 m-0 block py-3">
              <li
                v-for="exs in extraServices"
                :key="exs.id"
                class="py-1 translate-x-0 hover:translate-x-2 transition-all delay-100"
              >
                <router-link
                  :to="exs.link"
                  class="text-sm font-medium tracking-wide text-white"
                  >{{ exs.name }}</router-link
                >
              </li>
            </ul>
          </div>
        </div>
        <!-- 3rd part end -->

        <!-- 4th part -->
        <div class="flex justify-center px-2 w-1/4 h-auto">
          <div class="block">
            <span class="text-lg font-bold tracking-wide py-2 text-white"
              >Contact Information</span
            >
            <ul class="list-none py-3 m-0 block">
              <li
                v-for="addl in addressLink"
                :key="addl.id"
                class="py-1 translate-x-0 hover:translate-x-2 transition-all delay-100 text-sm font-medium tracking-wide text-white"
              >
                {{ addl.name }}
              </li>
            </ul>
          </div>
        </div>
        <!-- 4th part end -->
      </div>
    </div>
    <div class="flex justify-center py-2 bg-black ring-1 ring-white">
      <p class="text-sm font-normal text-gray-300">
        All RIght Reserved Logic Software Ltd.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      extraLink: [
        {
          id: 1,
          name: "Terms & Conditions",
          link: "#",
        },
        {
          id: 2,
          name: "About Company",
          link: "#",
        },
        {
          id: 3,
          name: "Payment Gatway",
          link: "#",
        },
        {
          id: 4,
          name: "Policy",
          link: "#",
        },
      ],
      extraServices: [
        {
          id: 1,
          name: "Data Security",
          link: "#",
        },
        {
          id: 2,
          name: "IT Managment",
          link: "#",
        },
        {
          id: 3,
          name: "Outsourcing",
          link: "#",
        },
        {
          id: 4,
          name: "Networking",
          link: "#",
        },
      ],
      addressLink: [
        {
          id: 1,
          name: "+8801600000000",
          icon: "",
        },
        {
          id: 2,
          name: "info@example.com",
          icon: "",
        },
        {
          id: 3,
          name: "Road:04,Banani,Dhaka",
          icon: "",
        },
      ],
    };
  },
};
</script>

<style scoped>
.footer-cover {
  background-image: url("../../assets/images/footer-bg2.jpg");
  background-position: center;
  background-size: cover;
  object-fit: cover;
}
</style>