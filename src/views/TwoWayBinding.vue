<template>
  <div id="twoWay">
    <div class="container mt-5">
      <div class="row">
        <div class="col-sm-3"></div>
        <div class="col-sm-6 text-center">
          <h3>Parent Component</h3>
          <input
            type="text"
            class="form-control"
            placeholder="Please input somthing"
            v-model="pageTitle"
          />
        </div>
        <div class="col-sm-3"></div>
      </div>
      <div class="row mt-5">
        <div class="col-sm-12 text-center">
          <h5>Parent Text</h5>
          <span>{{ pageTitle }}</span>
        </div>
      </div>
    </div>
  </div>
  <hr />
  <child-comp v-model:parentText="pageTitle" />
</template>
<script>
import ChildComp from "../components/TwoWay/Childcomp.vue";
export default {
  name: "TwoWayBinding",
  components: {
    ChildComp,
  },
  data() {
    return {
      pageTitle: "",
    };
  },
};
</script>
<style></style>
