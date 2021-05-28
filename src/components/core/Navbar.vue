<template>
  <div id="navbar" class="relative h-12 w-full bg-green-300">
    <div id="button bar" class="h-12 ml-8 w-1/4">
      <button
        class="bg-green-300 hover:bg-green-200 h-12 w-40 items-center justify-center text-white hover:text-white font-bold focus:outline-none"
      >
        <a class="" href=""> About Us </a>
      </button>
      <button
        class="bg-green-300 hover:bg-green-200 h-12 w-40 items-center justify-center text-white hover:text-white font-bold focus:outline-none"
      >
        <a class="" href=""> Store </a>
      </button>
    </div>
    <div class="absolute inset-x-12 top-3">
      <p class="text-white text-center mr-12 font-bold">+123 12345656</p>
    </div>
    <div class="absolute top-0 right-0">
      <button
        class="bg-red-500 hover:bg-green-500 h-12 w-40 items-center justify-center text-white hover:text-white font-bold focus:outline-none"
      >
        <router-link to="/cart">
          <p class="text-white hover:text-white">
            Total cart items: <span> {{ cartQuantity }}</span>
          </p>
        </router-link>
      </button>
    </div>
  </div>
</template>
<script>
import { mapGetters } from "vuex";
export default {
  name: "Navbar",
  computed: {
    ...mapGetters(["cartQuantity"]),
  },
  created() {
    this.$store.dispatch("getCartItems");
  },
};
</script>
