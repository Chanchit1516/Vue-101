<template>
  <div id="Home">
    <div class="container mt-5">
      <div class="row">
        <div class="col-sm-3 mt-4" v-for="item in postList" :key="item.Id">
          <div class="card">
            <div class="card-body">
              <div class="text-center">
                <i :class="item.Icon"></i>
                <h5 class="card-title text-center">{{ item.Title }}</h5>
                <a :href="item.Url" class="card-text" style="cursor: pointer">{{
                  item.Details
                }}</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      postList: [
        {
          Id: 0,
          Title: "Home",
          Details: "Go to home menu click here",
          Icon: "bx bx-grid-alt",
          Url: "/home",
        },
        {
          Id: 0,
          Title: "TwoWay",
          Details: "Go to twoway menu click here",
          Icon: "bx bx-network-chart",
          Url: "/twowaybinding",
        },
        {
          Id: 0,
          Title: "Grid",
          Details: "Grid",
          Icon: "bx bxl-steam",
          Url: "/grid",
        },
        {
          Id: 0,
          Title: "About",
          Details: "Go to about menu click here",
          Icon: "bx bx-grid-alt",
          Url: "/about",
        },
        {
          Id: 0,
          Title: "Dashboard",
          Details: "Go to dashboard menu click here",
          Icon: "bx bx-grid-alt",
          Url: "/dashboard",
        },
        {
          Id: 1,
          Title: "User",
          Details: "Go to user menu click here",
          Icon: "bx bx-user",
          Url: "/user",
        },
        {
          Id: 2,
          Title: "Messages",
          Details: "Go to message menu click here",
          Icon: "bx bx-message-dots",
          Url: "/message",
        },
        {
          Id: 3,
          Title: "Analytics",
          Details: "Go to analytics menu click here",
          Icon: "bx bxs-analyse",
          Url: "/analytics",
        },
        {
          Id: 4,
          Title: "File Manager",
          Details: "Go to file menu click here",
          Icon: "bx bx-folder",
          Url: "/fileManager",
        },
        {
          Id: 5,
          Title: "Order",
          Details: "Go to order menu click here",
          Icon: "bx bx-cart",
          Url: "/order",
        },
      ],
    };
  },
  components: {},
};
</script>
<style>
#Home i {
  font-size: 60px !important;
}
</style>
