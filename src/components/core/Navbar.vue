<template>
  <div id="navbar" class="relative h-8 w-full bg-indigo-500">
    <div id="button bar" class="h-8 ml-8 w-1/4">
      <button class="h-full text-white hover:bg-indigo-700">
        <a class="" href=""> About Us </a>
      </button>
      <button class="h-full text-white hover:bg-indigo-700">
        <a class="" href=""> Store </a>
      </button>
    </div>
    <div class="absolute inset-x-5 top-0">
      <p class=" text-white text-center mr-8">
        +123 12345656
      </p>
    </div>
    <div class="absolute top-0 right-0">
      <button
        class="h-full text-white rounded-lg bg-indigo-400 hover:bg-indigo-700 mr-8"
      >
        <router-link to="/cart">
          <p>
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
