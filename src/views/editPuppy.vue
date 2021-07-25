<template>
  <div class="home">
    <h1>{{ message }}</h1>
    Name:<input type="text" v-model="editPuppyParams.name">
    Age:<input type="text" v-model="editPuppyParams.age">
    Breed:<input type="text" v-model="editPuppyParams.breed">
  </div>
</template>
<style></style>
<script>
export default {
  data: function() {
    return {
      message: "Edit Puppy",
      editPuppyParams: {}
    };
  },
  created: function() {},
  methods: {}
};
</script>