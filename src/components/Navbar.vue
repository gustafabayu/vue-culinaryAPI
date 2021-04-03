<template>
  <nav class="navbar navbar-expand-lg navbar-light">
    <div class="container">
      <a class="navbar-brand" href="#">Culinary</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/foods">Foods</router-link>
          </li>
        </ul>
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <router-link class="nav-link" to="/basket"
              >Basket <b-icon-bag></b-icon-bag
              ><span class="badge badge-success ml-2">{{
                qty_order.length
              }}</span></router-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import axios from "axios";

export default {
  name: "Navbar",
  data() {
    return {
      qty_order: [],
    };
  },
  methods: {
    setQty(data) {
      this.qty_order = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/keranjangs")
      .then((response) => this.setQty(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
</style>