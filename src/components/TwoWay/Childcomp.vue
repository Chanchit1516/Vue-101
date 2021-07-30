<template>
  <div id="Childcomp">
    <div class="container mt-5">
      <div class="row">
        <div class="col-sm-3"></div>
        <div class="col-sm-6 text-center">
          <h3>Child Component</h3>
          <input
            type="text"
            class="form-control"
            placeholder="Please input somthing"
            :value="parentText"
            @input="(event) => $emit('update:parentText', event.target.value)"
          />
        </div>
        <div class="col-sm-3"></div>
      </div>
      <div class="row mt-5">
        <div class="col-sm-12 text-center">
          <h5>Child Text</h5>
          <span>{{ parentText }}</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ChildComp",
  props: ["parentText"],
};
</script>
<style></style>
