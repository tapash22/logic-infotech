<template>
  <div class="home px-5 h-screen">
    <div class="block px-5 section">
      <span class="section-subtitle user-select-none">
        {{ product.name }}
      </span>
      <p class="section-title user-select-none">
        {{ product.text }}
      </p>
      <div class="grid grid-cols-3 gap-3 px-2 py-5">
        <div v-for="pc in product.carddetails" :key="pc.id">
          <SingleCard :pc="pc" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SingleCard from "@/components/card/SingleCard";

export default {
  data() {
    return {
      productId: null,
      product: {
        id: null,
        name: null,
        text: null,
        carddetails: [],
      },
    };
  },
  mounted() {
    const productId = this.$route.params.id;
    const storedProduct = this.$route.query.data;

    if (storedProduct) {
      this.product = JSON.parse(storedProduct);
    } else {
      this.fetchProductDetails(productId);
    }
  },

  components: {
    SingleCard,
  },

  methods: {
    fetchProductDetails(Id) {
      console.log(Id);
    },
  },
};
</script>