<template>
  <div class="container">
    <div class="row">
      <div class="col-12 text-center">
        <h3 class="pt-3">Add Category</h3>
      </div>
    </div>
    <div class="row">
      <div class="col-3"></div>
      <div class="col-6">
        <form>
          <div class="form-group">
            <label for="">Name</label>
            <input type="text" class="form-control" v-model="categoryName" />
          </div>
          <div class="form-group">
            <label for="">Description</label>
            <textarea type="text" class="form-control" v-model="description" />
          </div>
          <div class="form-group">
            <label for="">Image</label>
            <input type="text" class="form-control" v-model="imgUrl" />
          </div>
          <button
            class="btn btn-submit btn-primary"
            type="button"
            @click="addCategory"
          >
            Submit
          </button>
        </form>
      </div>
      <div class="col-3"></div>
    </div>
  </div>
</template>
<script>
const axios = require("axios");
const sweetalert = require("sweetalert");
export default {
  data() {
    return {
      categoryName: "",
      description: "",
      imgUrl: "",
    };
  },
  methods: {
    addCategory() {
      console.log(this.categoryName, this.description);
      const newCategory = {
        categoryName: this.categoryName,
        description: this.description,
        imgUrl: this.imgUrl,
      };
      const baserURL = "https://limitless-lake-55070.herokuapp.com";
      axios({
        method: "post",
        url: `${baserURL}/category/create`,
        data: JSON.stringify(newCategory),
        headers: {
          "content-type": "application/json",
        },
      })
        .then(() => {
          sweetalert({
            text: "category add successfully",
            icon: "success",
          });
        })
        .catch(() => {
          console.log();
        });
    },
  },
};
</script>

<style scoped></style>
