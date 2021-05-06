<template>
  <div class="v-cart-item">
    <img
      :src="require(`../assets/images/${cart_item_data.image}`)"
      :alt="`${cart_item_data.name}`"
      class="v-cart-item__img"
    />
    <div class="v-cart-item__info">
      <p class="v-cart-item__name v-cart-item__info-item">
        {{ cart_item_data.name }}
      </p>
      <p class="v-cart-item__price v-cart-item__info-item">
        {{ cart_item_data.price }}
      </p>
      <p class="v-cart-item__article v-cart-item__info-item">
        {{ cart_item_data.article }}
      </p>
    </div>
    <div class="v-cart-item__quantity">
      Quantity: {{ cart_item_data.quantity }}
    </div>
    <button @click="removeFromCart" class="v-cart-item__btn btn remove__btn">
      Remove
    </button>
  </div>
</template>

<script>
export default {
  name: "v-cart-item",
  comments: {},
  props: {
    cart_item_data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  data() {
    return {};
  },
  computed: {},
  methods: {
    removeFromCart() {
      this.$emit("removeFromCart");
    },
  },
  watch: {},
  mounted() {},
};
</script>
<style lang="scss">
.v-cart-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: nowrap;
  transition: 0.3s all ease-in-out;
  padding: $padding * 2;
  box-shadow: 0 0 8px $boxShadow;
  &__img {
    width: 80px;
    height: auto;
  }
  &__info {
    width: 80px;
  }
  &__name {
  }
  &__price {
  }
  &__article {
  }
  &__btn {
  }
}
</style>
