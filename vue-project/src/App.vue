<script>
import Homepage from "./components/Homepage.vue"
import Login from "./components/Login.vue"

export default {
  components: {
    Homepage,
    Login,
  },
  data: () => ({
    currentPage: "Home",
  }),
  methods: {
    showHomePage() {
      this.currentPage = "Home";
    },
    showLoginPage() {
      this.currentPage = "Login";
    },
  },
};
</script>

<template>
  <header class="header">
    <span class="logo">
      <img src="@/assets/vue-hat.png" width="30" /> hello vue
    </span>
    <nav class="nav">
      <a href="#" @click.prevent="showHomePage">Home</a>
      <a href="#" @click.prevent="showLoginPage">Login</a>
    </nav>
  </header>
  <Homepage v-if="currentPage === 'Home'" />
  <!-- you can also say <component is="Homepage"/> -->
  <Login v else />
</template>

<style>
* {
  box-sizing: border-box;
  font-family: "Inter", sans-serif;
  margin: 0;
  padding: 0;
}
</style>