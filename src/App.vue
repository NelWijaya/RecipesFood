<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-light bg-dark fixed-top">
      <div class="container">
        <router-link class="navbar-brand" to="/">
          <img
            src="./assets/icon.png"
            width="30"
            height="30"
            class="d-inline-block align-top"
            alt=""
            loading="lazy"
          />&nbsp;&nbsp;
          <span>Recipes Food</span>
        </router-link>
        <button
          class="navbar-toggler navbar-dark border-white"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav ml-auto" id="nav">
            <li class="nav-item">
              <router-link class="nav-link" to="/">Home</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/about">About Us</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/recipes">Recipes</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <section>
      <transition name="fade" mode="out-in">
        <router-view />
      </transition>
    </section>
    <Footer/>
  </div>
</template>
<script>
import Footer from "@/components/Footer.vue";
export default {
  components: {
    Footer,
  },
}
</script>

<style>
body {
  background-color: #fafafa;
  overflow-x: hidden;
}

#app {
  font-family: "Poppins", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  overflow: hidden;
  width: 100vw;
}

.navbar-brand span {
  color: white;
  font-weight: bold;
}

#nav a {
  font-weight: bold;
  color: white;
}

.dropdown-menu a {
  color: black !important;
}

#nav a.router-link-exact-active {
  color: #f16765;
  text-decoration: underline;
}

.border-white {
  border: 1px solid white im !important;
}

.btn-primary {
  background-color: #f16765;
  border: 1px solid #f16765;
}

.btn-primary:hover {
  background-color: #c45452;
  border: 1px solid #c45452;
}

.btn-primary:active {
  background-color: #ff8482;
  border: 1px solid #ff8482;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
  transform: translateX(2em);
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
}

.dropdown-menu{
  text-align: center;
}
::-webkit-scrollbar{
  width: 15px;
}
::-webkit-scrollbar-track{
  border: 5px solid #343a40;
  box-shadow: inset 0 0 2.5px 2px rgba(0,0,0,0.5);
}
::-webkit-scrollbar-thumb{
  background:linear-gradient(
    45deg,
    #f16765,
    #f1b065
  );
  border-radius: 5px;
}
</style>
