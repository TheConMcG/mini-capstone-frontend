<template>
  <div class="home">
    <h1>{{ message }}</h1>
  </div>
</template>

<style></style>

<script>
  import axios from 'axios'
  export default {
    data: function () {
      return {
        message: "Welcome to Vue.js!",
        products: [],
      };
    },
    created: function () {
      this.productsIndex();
    },
    methods: {
      productsIndex: function () {
        console.log("in the index");
        axios.get("/products").then(response => {
          console.log(response.data),
          this.products = response.data;
        })
      },
    },
  };
</script>
