<template>
  <div class="bg-login">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-sm-12">
          <div class="card center" style="width: 35rem">
            <div class="card-body">
              <h2 class="card-title text-center">Sign In</h2>
              <form
                class="mt-4"
                @submit="checkForm"
                action="/Home"
                method="get"
              >
                <p v-if="errors.length">
                  <b
                    >Please correct the following error(s):
                    <ul>
                      <li v-for="error in errors" :key="error">{{ error }}</li>
                    </ul></b
                  >
                </p>

                <div class="mb-3">
                  <label for="exampleInputUser1" class="form-label"
                    >Username</label
                  >
                  <input
                    type="text"
                    class="form-control"
                    id="exampleInputUser1"
                    placeholder="Username"
                    v-model="username"
                  />
                </div>
                <div class="mb-3">
                  <label for="exampleInputPassword1" class="form-label"
                    >Password</label
                  >
                  <input
                    type="password"
                    class="form-control"
                    id="exampleInputPassword1"
                    v-model="password"
                    placeholder="Password"
                  />
                </div>
                <div class="mb-3 form-check">
                  <input
                    type="checkbox"
                    class="form-check-input"
                    id="exampleCheck1"
                  />
                  <label class="form-check-label" for="exampleCheck1"
                    >Check me out</label
                  >
                </div>
                <div class="d-grid gap-2">
                  <button type="submit" class="btn btn-primary">Login</button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Login",
  data() {
    return {
      errors: [],
      username: null,
      password: null,
    };
  },
  methods: {
    checkForm: function (e) {
      this.errors = [];
      if (this.username == "admin" && this.password == "1234") {
        // this.$router.push("/home");
        window.location.href = "/home";
        return false;
      }

      if (!this.username) {
        this.errors.push("Username required.");
      }
      if (!this.password) {
        this.errors.push("Password required.");
      }

      if (!this.errors.length) {
        this.errors.push("Invalid username or password.");
      }

      e.preventDefault();
    },
  },
  watch: {
    username: function (val) {
      if (val) {
        this.errors = [];
      }
    },
    password: function (val) {
      if (val) {
        this.errors = [];
      }
    },
  },
};
</script>
<style>
.center {
  margin: auto;
  width: 50%;
  padding: 10px;
  margin-top: 20%;
}

.bg-login {
  width: 100vw;
  height: 100vh;
  background-color: rgb(190, 190, 190);
}
</style>
