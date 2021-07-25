<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="puppy in puppies">
      <p> {{ puppy.id }} </p>
      <p> {{ puppy.name }} </p>
      <p>--------------------------------------------------</p>
    </div>
  </div>
</template>
<style></style>
<script>
import axios from "axios";
export default {
  data: function() {
    return {
      message: "Look at all the Puppies",
      puppies: []
    };
  },
  created: function() {
    this.indexPuppies()
  },
  methods: {
    indexPuppies: function () {
      console.log("puppies index...")
      axios.get('http://localhost:3000/puppies').then((response) => {
      console.log(response);
      this.puppies = response.data;
      }) ;
    },
  }
};
</script>
