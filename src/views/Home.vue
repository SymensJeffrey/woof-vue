<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="puppy in puppies">
      <p> {{ puppy.id }} </p>
      <p> {{ puppy.name }} </p>
      <button v-on:click="showPuppy(puppy)">More info</button>
      <p>--------------------------------------------------</p>
    </div>
      <dialog id="puppy-info">
        <form method="dialog">
          <h1> {{ currentPuppy.name }} </h1>
          <p> {{ currentPuppy.age }} </p>
          <p> {{ currentPuppy.breed }} </p>
          <button>Close</button>
        </form>
      </dialog>
  </div>
</template>
<style></style>
<script>
import axios from "axios";
export default {
  data: function() {
    return {
      message: "Look at all the Puppies",
      puppies: [],
      currentPuppy: {},
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
    showPuppy: function (puppy) {
      console.log("showing puppy...");
      this.currentPuppy = puppy;
      document.querySelector("#puppy-info").showModal();
    },
  },
};
</script>
