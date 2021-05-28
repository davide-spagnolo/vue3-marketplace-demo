<template>
  <!--<div class="card bordered">
  <figure>
    <img src="https://picsum.photos/id/1005/400/250">
  </figure> 
  <div class="card-body">
    <h2 class="card-title">Top image
      <div class="badge mx-2 badge-secondary">NEW</div>
    </h2> 
    <p>Rerum reiciendis beatae tenetur excepturi aut pariatur est eos. Sit sit necessitatibus veritatis sed molestiae voluptates incidunt iure sapiente.</p> 
    <div class="justify-end card-actions">
      <button class="btn btn-secondary">More info</button>
    </div>
  </div>
</div> -->

  <div class="card bordered">
    <figure>
      <img
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
          <a
            class="button is-primary is-pulled-right"
            @click="addCartItem(productItem)"
          >
            <strong>Add to Cart</strong>
          </a>
          <a class="button is-primary is-light is-pulled-left">
            <strong>$ {{ productItem.fields.price }}</strong>
          </a>
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
