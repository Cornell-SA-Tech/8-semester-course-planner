<template>
  <div class="container">
    <div class="jumbotron" id="home-card">
      <h3>Please input your destination below</h3>
      <hr>
      <p><el-button type="primary" @click="goGame">From</el-button></p>
      <el-input placeholder="where are you?" v-model="fromLoc"></el-input>

      <p><el-button type="primary" @click="goHistory">To</el-button></p>
      <el-input placeholder="what's your destination?" v-model="toLoc"></el-input>

      <div class="block">
        <span class="demonstration">Date and time</span>
        <el-date-picker
          v-model="value1"
          type="datetime"
          placeholder="Select date and time">
        </el-date-picker>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        fromLoc: '',
        toLoc: '',
        value1: ''
      }
    },
    props: ['currGameLevel'],
    methods: {
      goHistory() {
        this.$router.push('/history');
      },
      goGame() {
        this.$router.push('/game/' + this.currGameLevel);
      }
    }
  }
</script>

<style type="text/css">
  #home-card {
    margin-top: 3rem;
    background-color: rgba(255,255,255,0.7);
    text-align: center;
  }
</style>