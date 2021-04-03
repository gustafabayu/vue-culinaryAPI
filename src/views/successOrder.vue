<template>
  <div class="successOrder">
    <Navbar />
    <div class="container">
      <div class="row justify-content-center mt-3">
        <div class="col text-center">
          <img src="../assets/image/menunggu.png" width="300" />
          <h2>Order Success!!</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";

export default {
  name: "successOrder",
  components: {
    Navbar,
  },
};
</script>

<style>
</style>