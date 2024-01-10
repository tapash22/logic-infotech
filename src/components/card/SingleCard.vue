<template>
  <div   class="relative group bg-white px-2 py-2 block shadow-lg shadow-gray-300 rounded-lg w-full h-auto overflow-hidden transition-all duration-300 transform ">
    <div class="overflow-hidden">
        <img :src="pc.image" class="scale-100 hover:scale-110 transition-all" />
    </div>
    <div
      class="hidden p-3 text-center transform translate-y-full bg-white group-hover:block group-hover:opacity-100 group-hover:translate-y-0"
    >
      <router-link
        :to="pc.link"
        class="text-lg font-bold tracking-wide text-black hover:text-indigo-950 uppercase py-2 flex justify-start"
      >
        {{ pc.name }}
      </router-link>
      <p class="font-normal text-sm tracking-normal text-justify">
        {{ pc.message }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["pc"],
};
</script>