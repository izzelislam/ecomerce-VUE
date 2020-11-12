<template>
  <div>
    <!-- Women Banner Section Begin -->
    <section class="women-banner spad">
      <div class="container-fluid">
        <div class="row">
          <div class="col-lg-12 mt-5" v-if="products.length > 0">
            <carousel
              class="product-slider"
              :autoplay="true"
              :item="3"
              :nav="false"
            >
              <div
                class="product-item"
                v-for="itemProduct in products"
                :key="itemProduct.id"
              >
                <div class="pi-pic">
                  <img :src="itemProduct.galleries[0].photo" alt="" />
                  <ul>
                    <li class="w-icon active">
                      <a href="#"><i class="icon_bag_alt"></i></a>
                    </li>
                    <li class="quick-view">
                      <router-link :to="'/product/' + itemProduct.id">
                        + Quick View
                      </router-link>
                    </li>
                  </ul>
                </div>
                <div class="pi-text">
                  <div class="catagory-name">{{ itemProduct.type }}</div>
                  <router-link to="/product">
                    <a href="/product">
                      <h5>{{ itemProduct.name }}</h5>
                    </a>
                  </router-link>
                  <div class="product-price">
                    ${{ itemProduct.price }}
                    <span>$35.00</span>
                  </div>
                </div>
              </div>
            </carousel>
          </div>
          <div class="col-lg-12 mt-5" v-else>
            <p>Produk tidak di temukan</p>
          </div>
        </div>
      </div>
    </section>
    <!-- Women Banner Section End -->
  </div>
</template>

<script>
import carousel from "vue-owl-carousel";
import axios from "axios";

export default {
  name: "ProductShyna",
  components: {
    carousel,
  },
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    axios
      .get("http://localhost:8000/api/products")
      .then((res) => (this.products = res.data.data.data))

      .catch((err) => console.log(err));
  },
};
</script>

<style scoped>
.product-item {
  margin-left: 10px;
  margin-right: 10px;
}
</style>
