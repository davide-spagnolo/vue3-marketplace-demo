<template>
  <div class="card bordered rounded-lg">
    <figure>
      <img
        class="rounded-t-lg"
        v-bind:src="`${publicPath}` + productItem.fields.image.fields.file.url"
      />
    </figure>
    <div class="card-body">
      <div class="content">
        <h4>{{ productItem.fields.title }}</h4>
      </div>
      <div class="media">
        <div class="media-content">
          <!--<p class="title is-6">{{ productItem.owner }}</p>
            <p class="subtitle is-7">{{ productItem.email }}</p>-->
        </div>

        <div class="">
          <button
            class="bg-green-100 rounded-tl-lg h-10 w-24 text-green-500 font-bold focus:outline-none"
            style="cursor: default"
          >
            $ {{ productItem.fields.price }}
          </button>
          <button
            class="bg-red-500 hover:bg-green-500 rounded-br-lg h-10 w-24 items-center justify-center text-white hover:text-white font-bold focus:outline-none active:bg-green-700"
            @click="addCartItem(productItem)"
          >
            Add to Cart
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  name: "ProductListItem",
  props: ["productItem"],
  methods: {
    ...mapActions(["addCartItem"]),
  },
  data() {
    return {
      publicPath: process.env.BASE_URL,
    };
  },
};
</script>
