<template>
  <head>
    <link
      rel="stylesheet"
      href="https://unpkg.com/boxicons@latest/css/boxicons.min.css"
    />
  </head>
  <div class="sidebar" v-bind:class="{ active: isActive }">
    <div class="logo_content">
      <div class="logo">
        <i class="bx bxl-visual-studio"></i>
        <div class="logo_name">CodingLab</div>
      </div>
      <i class="bx bx-menu" id="btn" v-on:click="setActive()"></i>
    </div>
    <ul class="nav_list">
      <li>
        <i class="bx bx-search" v-on:click="setActive()"></i>
        <input type="text" v-model="search" placeholder="Search..." />
        <span class="tooltip">Search</span>
      </li>
      <li v-for="item in filteredList" :key="item.Id">
        <a href="#">
          <i :class="item.Icon"></i>
          <span class="links_name">{{ item.Title }}</span>
        </a>
        <span class="tooltip">{{ item.tooltip }}</span>
      </li>
    </ul>
    <div class="profile_content">
      <div class="profile">
        <div class="profile_details">
          <img src="../assets/Profile.png" alt="" />
          <div class="name_job">
            <div class="name">Mr.Oat</div>
            <div class="job">Web Developer</div>
          </div>
        </div>
        <i class="bx bx-log-out" id="log_out" v-on:click="logout()"></i>
      </div>
    </div>
  </div>
  <div class="home_content">
    <div class="text">
      <span>Home Content</span>
    </div>
    <div class="container text-center">
      <div class="row">
        <div class="col-sm-4">col</div>
        <div class="col-sm-4">col</div>
        <div class="col-sm-4">col</div>
      </div>
    </div>
  </div>
</template>
<script>
import "../assets/css/navbar.css";
export default {
  name: "Navbar",
  data() {
    return {
      isActive: false,
      search: "",
      postList: [
        {
          Id: 0,
          Title: "Dashboard",
          tooltip: "Dashboard",
          Icon: "bx bx-grid-alt",
        },
        {
          Id: 1,
          Title: "User",
          tooltip: "User",
          Icon: "bx bx-user",
        },
        {
          Id: 2,
          Title: "Messages",
          tooltip: "Messages",
          Icon: "bx bx-message-dots",
        },
        {
          Id: 3,
          Title: "Analytics",
          tooltip: "Analytics",
          Icon: "bx bxs-analyse",
        },
        {
          Id: 4,
          Title: "File Manager",
          tooltip: "File Manager",
          Icon: "bx bx-folder",
        },
        {
          Id: 5,
          Title: "Order",
          tooltip: "Order",
          Icon: "bx bx-cart",
        },
      ],
    };
  },
  methods: {
    setActive: function () {
      this.isActive = !this.isActive;
    },
    logout: function () {
      this.$router.push("/");
    },
  },
  computed: {
    filteredList() {
      return this.postList.filter((post) => {
        return post.Title.toLowerCase().includes(this.search.toLowerCase());
      });
    },
  },
};
</script>
<style></style>
