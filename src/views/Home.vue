<template>
  <div class="home">
    <sui-container>
      <sui-header
        style="font-size: 50px; margin-top: 1rem;"
      >
        Indigo Test
      </sui-header>

      <sui-card-group :items-per-row="3">
        <sui-card
          v-for="product in products"
          :key="product.id"
        >
          <sui-image
            :src="product.image"
          />
          <sui-card-content>
            <sui-card-header>
              {{ product.name }}
            </sui-card-header>
            <sui-card-description>
              {{ product.description }}
            </sui-card-description>
          </sui-card-content>
          <sui-card-content extra>
            <router-link
              :to="`product/${product.id}`"
            >
              <sui-icon name="shopping cart" />
              Buy now!
            </router-link>
          </sui-card-content>
        </sui-card>
      </sui-card-group>
    </sui-container>
  </div>
</template>

<script>
import fetch from 'isomorphic-fetch';
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
  },
  async mounted() {
    const get = await fetch('http://localhost:3000/api/products');

    const result = await get.json();

    this.products = result.products;
    console.log(this.products);
  },
  data() {
    return {
      products: [],
    };
  },
};
</script>
