<template>
  <div class="container">
    <div class="row">
      <div class="col-12 text-center">
        <h3 class="pt-3">Our Categories</h3>
      </div>
    </div>
    <div class="row">
      <div v-for="category in categories" :key="category.id" class="col-md-4">
        <CategoryBox :category="category" />
        <!-- Ensure this line is present -->
      </div>
    </div>
  </div>
</template>
<script>
import CategoryBox from "@/components/category/CategoryBox.vue";

const axios = require("axios");
export default {
  data() {
    return {
      baserURL: "https://limitless-lake-55070.herokuapp.com",
      categories: [],
    };
  },
  components: {
    CategoryBox, // This should be here
  },

  methods: {
    async getCategories() {
      await axios
        .get(`${this.baserURL}/category/`)
        .then((res) => (this.categories = res.data))
        .catch((err) => console.log(err));
    },
  },
  mounted() {
    this.getCategories();
  },
};
</script>

<style scoped></style>
