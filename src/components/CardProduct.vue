<template>
  <div class="card shadow card-product">
    <img
      :src="'assets/images/' + product.gambar"
      class="card-img-top"
      alt="..."
    />
    <div class="card-body">
      <h5 class="card-title">{{ product.nama }}</h5>
      <p class="card-text">Harga : Rp. {{ _formatPrice(product.harga) }}</p>
      <router-link class="btn btn-success" :to="'/foods/' + product.id"
        ><b-icon-cart></b-icon-cart> Pesan</router-link
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product"],
  methods: {
    _formatPrice(value) {
      const val = (value / 1).toFixed(0).replace(".", ",");
      return val.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".");
    },
  },
};
</script>

<style></style>
