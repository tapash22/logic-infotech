<template>
  <div class="block w-full footer-cover mt-5 relative">
    <!-- subscribe box -->
    <div class="w-full h-auto px-6 py-5 flex justify-center">
      <form
        class="flex justify-center py-5 px-4 bg-yellow-500 w-5/6 rounded-lg items-center"
        style="margin-top: -80px"
      >
        <p class="text-xl font-bold py-1 w-1/3">Subscribe to our newsletter</p>
        <input
          type="text"
          class="h-12 rounded-bl-lg rounded-tl-lg py-2 px-2 w-full bg-white ring-1 ring-white"
        />
        <button
          class="bg-black h-12 rounded-tr-lg rounded-br-lg text-white text-sm font-bold px-2"
        >
          Subscribe
        </button>
      </form>
    </div>
    <!-- subscribe box end -->
    <div class="px-10 py-2 flex justify-center w-full footer-cover">
      <div class="w-full h-auto px-3 py-1 flex justify-start">
        <!-- 1st part -->
        <div class="block px-2 w-1/4 h-auto">
          <img
            src="../../assets/logo/footer-logo.png"
            class="w-24 h-14 flex justify-center px-2"
          />
          <p
            class="font-normal text-sm text-white tracking-wide text-justify mr-7 py-3"
          >
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
            <span class="text-lg font-bold tracking-wide py-2 text-white underline underline-offset-8 decoration-gray-300"
              >Useful Links</span
            >
            <ul class="list-none p-0 m-0 block py-3">
              <li
                v-for="exl in extraLink"
                :key="exl.id"
                class="py-1 translate-x-0 hover:translate-x-2 transition-all delay-100  text-center"
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
            <span class="text-lg font-bold tracking-wide py-2 text-white underline underline-offset-8 decoration-gray-300"
              >Our Services</span
            >

            <ul class="list-none p-0 m-0 block py-3">
              <li
                v-for="exs in extraServices"
                :key="exs.id"
                class="py-1 translate-x-0 hover:translate-x-2 transition-all delay-100  text-center"
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
            <span class="text-lg font-bold tracking-wide py-2 text-white underline underline-offset-8 decoration-gray-300"
              >Contact Information</span
            >
            <ul class="list-none py-3 m-0 block">
              <li
                v-for="addl in addressLink"
                :key="addl.id"
                class="py-1 translate-x-0 hover:translate-x-2 transition-all delay-100 text-sm font-medium tracking-wide text-white text-center"
              >
                {{ addl.name }}
              </li>
            </ul>
            <ul class="flex justify-center py-2 px-2 list-none gap-3">
            <li>
              <a href=""><i class="fa fa-facebook-square text-2xl text-white"></i></a>
            </li>
            <li>
              <a href=""><i class="fa fa-linkedin text-2xl text-white"></i></a>
            </li>
            
            <li>
              <a href=""><i class="fa fa-instagram text-2xl text-white"></i></a>
            </li>
          
          </ul>
          </div>
        </div>
        <!-- 4th part end -->
      </div>
    </div>

    <!-- footer bottom -->
    <div class="flex justify-center py-2 bg-black ring-1 ring-white">
      <p class="text-sm font-normal text-gray-300">
        All Right Reserved Logic Software Ltd.
      </p>
    </div>
    <!-- footer bottom end -->
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
          name: "Privacy & Policy",
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