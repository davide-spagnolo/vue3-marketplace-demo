<template>
  <div class="box">
    <div class="cart-item__details">
      <p class="is-inline">{{ cartItem.title }}</p>
      <div>
        <span class="cart-item--price has-text-info has-text-weight-bold">
          ${{ cartItem.price }} X {{ cartItem.quantity }}
        </span>

        <div>
          <button @click="addCartItemQuantity(cartItem)"></button>
          <button @click="removeCartItem(cartItem)"></button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  name: "CartListItem",
  props: ["cartItem"],
  methods: {
    ...mapActions(["addCartItem", "removeCartItem", "addCartItemQuantity"]),
  },
};
</script>
