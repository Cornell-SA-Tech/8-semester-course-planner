<template>
  <div>
    <h3 style="text-align: center;">My Google Maps Demo</h3>
    <div id="map"></div>

    <el-button type="primary" @click="getCurrLoc()">Current location</el-button>
  </div>
</template>


<script>
  export default {
    data() {
      return {
      }
    },
    methods: {
      getCurrLoc() {
        console.log('curr');
      }
    }
    // watch: {
    // '$route' (to, from) {
    //   location.reload();
    // }
  }
</script>

<style type="text/css">
  #map {
    width: 50%;
    height: 400px;
    background-color: grey;
    margin-left: 25%;
  }
</style>