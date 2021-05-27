<template>
  <div>
    <Navbar />
    <div class="container mt-6">
      <div class="columns">
        <!--   <div class="column is-12 column--align-center">
          <router-view></router-view>
        </div> -->
      </div>
    </div>
    <ProductList />
  </div>
</template>
<script>
import Navbar from "./components/core/Navbar";
import ProductList from "./components/product/Product_List";
export default {
  name: "App",
  components: {
    Navbar,
    ProductList,
  },
};
</script>
<style>
html,
body {
  height: 100%;
  background: #f2f6fa;
}
</style>
