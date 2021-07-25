<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <p> <input type="text" v-model="newPuppyParams.name"
  </div>
</template>

<style></style>

<script>
  export default {
    data: function () {
      return {
        message: "Add New Puppy",
      };
    },
    created: function () {},
    methods: {},
  };
</script>
