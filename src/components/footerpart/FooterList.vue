<template>
    <ul class="list-none p-0 m-0 block py-3">
              <li
                v-for="exl in listData"
                :key="exl.id"
                class="py-1 translate-x-0 hover:translate-x-2 transition-all delay-100  text-center"
              >
                <router-link v-if="exl.link"
                  :to="exl.link"
                  class="text-sm font-medium tracking-wide text-white"
                  >{{ exl.name }}</router-link
                >
              </li>
            </ul>
</template>

<script>
export default {
    props:['listData']
}
</script>