<template>
  <div class="container">
    <div class="jumbotron" id="home-card">
      <el-row type="flex" class="row-bg" justify="center">
        <h3>Please input your destination below</h3>
      </el-row>
      <hr>

      <el-row type="flex" class="row-bg" justify="start">
        <p>From:</p>
        <el-input placeholder="where are you?" v-model="fromLoc"></el-input>
      </el-row>

      <el-row type="flex" class="row-bg" justify="start">
        <!-- <vue-timepicker></vue-timepicker> -->
      </el-row>


      <el-row type="flex" class="row-bg" justify="start">
        <p>To:</p>
        <el-input placeholder="what's your destination?" v-model="toLoc"></el-input>
      </el-row>

      <el-date-picker
        v-model="pickedDate"
        type="date"
        placeholder="Pick a day">
      </el-date-picker>


      <el-time-select
        v-model="pickedTime"
        :picker-options="{
          start: '00:00',
          step: '00:01',
          end: '23:59'
        }"
        placeholder="Select time">
      </el-time-select>
    </div>



  </div>
</template>

<script>
  export default {
    data() {
      return {
        pickedDate: '',
        pickedTime: ''
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