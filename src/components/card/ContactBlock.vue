<template>
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
</template>

<script>
export default {
    props:['addressLink']
}
</script>