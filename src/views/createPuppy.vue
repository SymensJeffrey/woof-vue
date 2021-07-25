<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <p> Name:<input type="text" v-model="newPuppyParams.name"> </p>
    <p> Age:<input type="text" v-model="newPuppyParams.age"> </p>
    <p> Breed:<input type="text" v-model="newPuppyParams.breed"> </p>
    <button v-on:click="createPuppy()"> Add Puppy </button>
  </div>
</template>

<style></style>

<script>
  import axios from "axios"
  export default {
    data: function () {
      return {
        message: "Add New Puppy",
        newPuppyParams: {}
      };
    },
    created: function () {},
    methods: {
      createPuppy: function () {
        console.log("creating puppy....")
        axios.post('http://localhost:3000/puppies', this.newPuppyParams).then((response) => {
          console.log(response.data)
          this.newPuppyParams = {};
          this.$router.push("/");
        });
      }
    },
  };
</script>
