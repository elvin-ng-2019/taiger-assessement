<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/github.png">
    <h1>elvin's github project</h1>
    <p>
      this is a single-page application that shows you a user's github projects and its respective documentation.
      simply:
      <!-- <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>. -->
    </p>
    <ol class='text-center'>
      <li>enter a github username</li>
      <li>the user's github projects will be shown</li>
    </ol>
    <br>
    <Search/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Search from '@/components/Search.vue' // @ is an alias to /src

export default defineComponent({
  name: 'Home',
  components: {
    Search
  }
})
</script>
<style scoped lang="scss">
  img {
    width: 10rem
  }
</style>
