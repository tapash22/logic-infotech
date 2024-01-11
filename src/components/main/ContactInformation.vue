<template>
    <div class="w-1/2 h-auto block px-3 py-3">
        <h1
          class="font-bold tracking-wide flex justify-start px-2 text-3xl border-l-4 border-indigo-500 mr-36 mb-5 user-select-none"
        >
          To make requests for further information, contact us
        </h1>
        <div
          class="flex w-full my-2 py-3 px-2"
          v-for="info in information"
          :key="info.id"
        >
          <div class="w-1/4 h-auto flex justify-center items-center">
            <i
              :class="info.icon"
              class="text-6xl fonr-bold text-indigo-950"
            ></i>
          </div>
          <div class="w-2/4 block px-1">
            <h3 class="font-bold tracking-normal flex justify-start text-2xl">
              {{ info.property }}
            </h3>
            <p class="break-all text-sm font-bold text-black mr-16">
              {{ info.value }}
            </p>
          </div>
        </div>
      </div>
</template>

<script>
export default {
    props:["title","information"]
}
</script>