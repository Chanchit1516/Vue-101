<template>
  <head>
    <link
      rel="stylesheet"
      href="https://unpkg.com/boxicons@latest/css/boxicons.min.css"
    />
  </head>
  <div
    class="sidebar"
    v-bind:class="{ active: isActive }"
    v-if="checkPathUrl() == true"
  >
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
        <a v-bind:href="item.Url">
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

  <div v-bind:class="{ home_content: checkPathUrl() }">
    <!-- <div style="height: 50px; background-color: #343a40"></div> -->
    <router-view />
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
          Title: "Home",
          tooltip: "Home",
          Icon: "bx bx-grid-alt",
          Url: "/home",
        },
        {
          Id: 0,
          Title: "TwoWay",
          tooltip: "Two way binding",
          Icon: "bx bx-network-chart",
          Url: "/twowaybinding",
        },
        {
          Id: 0,
          Title: "Grid",
          tooltip: "Grid",
          Icon: "bx bxl-steam",
          Url: "/grid",
        },
        {
          Id: 0,
          Title: "About",
          tooltip: "About",
          Icon: "bx bx-grid-alt",
          Url: "/about",
        },
        {
          Id: 0,
          Title: "Dashboard",
          tooltip: "Dashboard",
          Icon: "bx bx-grid-alt",
          Url: "/dashboard",
        },
        {
          Id: 1,
          Title: "User",
          tooltip: "User",
          Icon: "bx bx-user",
          Url: "/user",
        },
        {
          Id: 2,
          Title: "Messages",
          tooltip: "Messages",
          Icon: "bx bx-message-dots",
          Url: "/message",
        },
        {
          Id: 3,
          Title: "Analytics",
          tooltip: "Analytics",
          Icon: "bx bxs-analyse",
          Url: "/analytics",
        },
        {
          Id: 4,
          Title: "File Manager",
          tooltip: "File Manager",
          Icon: "bx bx-folder",
          Url: "/fileManager",
        },
        {
          Id: 5,
          Title: "Order",
          tooltip: "Order",
          Icon: "bx bx-cart",
          Url: "/order",
        },
      ],
    };
  },
  methods: {
    setActive: function () {
      this.isActive = !this.isActive;
    },
    logout: function () {
      window.location.href = "/";
      //   this.$router.push("/");
    },
    checkPathUrl: function () {
      if (window.location.pathname != "/") {
        return true;
      } else {
        return false;
      }
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
