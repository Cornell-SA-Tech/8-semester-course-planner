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

      <div class="block">
        <span class="demonstration">Default</span>
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
        pickerOptions1: {
          shortcuts: [{
            text: 'Today',
            onClick(picker) {
              picker.$emit('pick', new Date());
            }
          }, {
            text: 'Yesterday',
            onClick(picker) {
              const date = new Date();
              date.setTime(date.getTime() - 3600 * 1000 * 24);
              picker.$emit('pick', date);
            }
          }, {
            text: 'A week ago',
            onClick(picker) {
              const date = new Date();
              date.setTime(date.getTime() - 3600 * 1000 * 24 * 7);
              picker.$emit('pick', date);
            }
          }]
        },
        value1: '',
        value2: ''
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