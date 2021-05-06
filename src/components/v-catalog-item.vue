<template>
  <div class="v-catalog-item">
    <img
      :src="require(`../assets/images/${product_data.image}`)"
      :alt="`${product_data.name}`"
      class="v-catalog-item__img"
    />
    <p class="v-catalog-item__name">{{ product_data.name }}</p>
    <p class="v-catalog-item__price">Price: {{ product_data.price }}$</p>
    <button class="v-catalog-item__btn btn" @click="sendDataToParents">
      Add to card
    </button>
  </div>
</template>

<script>
export default {
  name: "v-catalog-item",
  comments: {},
  props: {
    product_data: {
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
    sendDataToParents() {
      this.$emit("sendArticle", this.product_data.article);
    },
  },
  watch: {},
  mounted() {},
};
</script>
<style lang="scss">
.v-catalog-item {
  flex: 0 0 23%;
  margin: $margin;
  padding: $padding * 2;
  box-shadow: 0 0 8px #e8c0e0;
  &__img {
    width: 100px;
    height: auto;
  }
}
</style>
