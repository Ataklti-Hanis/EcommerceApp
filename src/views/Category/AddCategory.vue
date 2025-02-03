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
            <label for="">Category Name</label>
            <input type="text" class="form-control" />
          </div>
          <div class="form-group">
            <label for="">Category Description</label>
            <input type="text" class="form-control" />
          </div>
          <div class="form-group">
            <label for="">Category Image</label>
            <input type="text" class="form-control" />
          </div>
          <button type="submit">Submit</button>
        </form>
      </div>
      <div class="col-3"></div>
    </div>
  </div>
</template>
<script>
export default {
  setup() {},
};
</script>

<style scoped></style>
