<template>
  <div class="hello">
    <input type="text" placeholder="input github user here!" class="mb-4" v-model="userinput" @keyup.enter="doThis()">
    <a class="btn" @click="doThis()">enter</a>
    <br>
    <h4 v-if="hasSearched" class="mt-3">showing {{resultLength}}  projects from <i>{{userinput}}</i></h4>
    <p v-else>not results yet</p>
    <div class="parallax">
    <div v-for="result in resultArray" :key="result.id" class="pt-1">
      <div class="card text-dark">
        <div class="card-header">
            Project ID = {{result.id}}
        </div>
        <div class="card-body">
            <h5 class="card-title">name: {{result.name}}</h5>
            <p v-if="result.description == undefined" class="card-text">no description specified</p>
            <p v-else class="card-description">{{result.description}}</p>
            <a :href='result.html_url' class="btn btn-primary mx-3">visit this repository</a>
            <a :href='result.html_url + "#readme"' class="btn btn-primary">view its readMe</a>
        </div>
    </div>
    </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import axios from 'axios'
export default defineComponent({
  data: function () {
    return {
      userinput: '',
      resultArray: [],
      hasSearched: false,
      resultLength: 0
    }
  },
  methods: {
    doThis: function () {
      var searchText = this.userinput
      var url = `https://api.github.com/users/${searchText}/repos`

      axios.get(url)
        .then(response => {
          this.resultArray = response.data
          this.resultLength = this.resultArray.length
          this.hasSearched = true
          console.log(this.resultArray)
        })
        .catch(error => alert(error))
    }
  }
})

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import'~bootstrap/dist/css/bootstrap.css';

.card {
  margin: 3rem;
}

.card-description {
  color: tan;
  font-weight: bold;
}

</style>
