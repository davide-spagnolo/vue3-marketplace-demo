<template>
  <div class="grid md:grid-flow-col grid-cols-3 grid-rows-3 gap-4">
    <div
      class="tile is-parent"
      v-for="productItem in productItems.items"
      :key="productItem.sys.id"
    >
      <ProductListItem :productItem="productItem" />
    </div>
  </div>
</template>
<script>
import { mapGetters } from "vuex";
import Product_List_Item from "./Product_List_Item";
export default {
  name: "ProductList",
  components: {
    ProductListItem: Product_List_Item,
  },
  computed: {
    ...mapGetters(["productItems"]),
  },
  created() {
    this.$store.dispatch("getProductItems");
  },
};
</script>
