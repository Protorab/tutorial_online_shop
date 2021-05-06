<template>
  <div class="v-catalog">
    <h1>{{ title }}</h1>
    <div class="v-catalog__list">
      <v-catalog-item
        v-for="product in PRODUCTS"
        :key="product.article"
        :product_data="product"
        @sendArticle="showChildConsole"
      />
    </div>
  </div>
</template>

<script>
import vCatalogItem from "./v-catalog-item";
import { mapActions, mapGetters } from "vuex";

export default {
  name: "v-catalog",
  components: {
    vCatalogItem,
  },
  props: {},
  data() {
    return {
      products: [
        {
          image: "1.jpg",
          name: "T-shirt 1",
          price: 100,
          article: "T1",
          available: true,
          category: "Мужские",
        },
        {
          image: "2.jpg",
          name: "T-shirt 2",
          price: 2100,
          article: "T2",
          available: true,
          category: "Женские",
        },
        {
          image: "3.jpg",
          name: "T-shirt 3",
          price: 200,
          article: "T3",
          available: true,
          category: "Мужские",
        },
        {
          image: "4.jpg",
          name: "T-shirt 4",
          price: 200,
          article: "T4",
          available: true,
          category: "Женские",
        },
        {
          image: "5.jpg",
          name: "T-shirt 5",
          price: 200,
          article: "T5",
          available: true,
          category: "Женские",
        },
        {
          image: "6.jpeg",
          name: "T-shirt 6",
          price: 100,
          article: "T6",
          available: true,
          category: "Женские",
        },
      ],
      title: "Catalog",
    };
  },
  computed: {
    ...mapGetters(["PRODUCTS"]),
  },
  methods: {
    ...mapActions(["GET_PRODUCTS_FROM_API"]),
    showChildConsole(data) {
      console.log(data);
    },
  },
  watch: {},
  mounted() {
    this.GET_PRODUCTS_FROM_API();
  },
};
</script>

<style lang="scss">
.v-catalog {
  margin-top: $margin;
  margin-bottom: $margin;

  &__list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    margin: -$margin;
  }
}
</style>
