<template>
<div class="container">
  <div id="nav">
  </div>
  <router-view/>
  </div>
  <br>
  <app-footer />
</template>
<script>
import AppFooter from '@/components/AppFooter.vue'

export default {
  components: {
    AppFooter
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Raleway&display=swap');
@import'~bootstrap/dist/css/bootstrap.css';

#app {
  font-family: 'Raleway', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  // background: rgb(255,255,255);
  // background-image: url("assets/background.jpg");
  // background-size: cover;
  // background: linear-gradient(0deg, rgba(255,255,255,1) 0%, rgba(36,171,186,1) 100%);
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #fff;
    }
  }
}
.parallax {
  /* The image used */
  background-image: url("assets/background.jpg");

  /* Set a specific height */
  min-height: 500px;

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
