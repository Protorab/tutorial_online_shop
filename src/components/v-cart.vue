<template>
  <div class="v-cart">
    <v-cart-item
      v-for="(item, index) in cart_data"
      :key="item.article"
      :cart_item_data="item"
      @removeFromCart="removeFromCart(index)"
    />
  </div>
</template>

<script>
import vCartItem from "./v-cart-item";
import { mapActions } from "vuex";
export default {
  name: "v-cart",
  components: {
    vCartItem,
  },
  comments: {},
  props: {
    cart_data: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {};
  },
  computed: {},
  methods: {
    ...mapActions(["REMOVE_FROM_CART"]),
    removeFromCart(index) {
      this.REMOVE_FROM_CART(index);
    },
  },
  watch: {},
  mounted() {},
};
</script>
<style lang="scss">
.v-cart {
  margin-top: $margin * 3;
  margin-bottom: $margin * 3;
}
</style>
