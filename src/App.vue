<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light" style="background-color:#aafabf">
      <router-link class="navbar-brand" to="/">TidChat</router-link>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <router-link class="nav-link" to="/about">Home</router-link>
          <a class="nav-link" href="#">Pricing</a>
          <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
        </div>
      </div>
      <a
        class="nav-link btn btn-outline-success my-2 my-sm-0"
        type="submit"
        data-toggle="modal"
        data-target="#login"
      >Login</a>
    </nav>
    <router-view></router-view>
    <div class="modal fade" id="login" tabindex="-1" role="dialog">
      <div id="alert" class="alert alert-danger" role="alert" style="display:none">กรุณาใส่ Username</div>
      <div
        id="alert2"
        class="alert alert-danger"
        role="alert"
        style="display:none"
      >กรุณาใส่ Password</div>
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Login</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <label for="username">Username</label>
            <input type="text" class="form-control" v-model="username" name="username" />
            <label for="password">Password</label>
            <input type="password" class="form-control" v-model="password" name="password" />
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-outline-success" @click="checkForm()">Login</button>
            <button type="button" class="btn btn-outline-primary">Register</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "app",
  data() {
    return {
      username: null,
      password: null,
    };
  },
  methods: {
    checkForm() {
      if (this.username && this.password) {
        document.getElementById("alert").style.display = "none";
        document.getElementById("alert2").style.display = "none";
      } else {
        if (!this.username) {
          document.getElementById("alert").style.display = "block";
        } else {
          document.getElementById("alert").style.display = "none";
        }

        if (!this.password) {
          document.getElementById("alert2").style.display = "block";
        } else {
          document.getElementById("alert2").style.display = "none";
        }
      }
    },
  },
};
</script>
<style>
#nav {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
#home {
  text-align: center;
}
</style>
