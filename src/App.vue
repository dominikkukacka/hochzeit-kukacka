<template>
  <div class="container">
    <div class="row">
      <div class="title col-sm-6">
        <h1>{{ title }}</h1>
        <h1>{{ marry }}</h1>
      </div>
    </div>
    <div class="row">
      <div class="countdown col-sm-6 pull-right">
        <Countdown date="2017-10-21T14:00:00+0200"></Countdown>
      </div>
    </div>
  </div>
</template>

<script>
  import Countdown from './components/Countdown.vue';

  export default {
    components: { Countdown },
    name: 'app',
    data () {
      return {
        title: 'Daniela & Dominik',
        marry: 'heiraten!'
      }
    }
  }
</script>

<style lang="scss">
  body {
    background: url('./assets/background.jpg') no-repeat center center fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    z-index: 100;
  }
  @media (min-width: 1200px) {
    .container {
      max-width: 1600px;
      width: 100%;
      padding: 0px;
    }
  }
  .title {
    margin-top: 10vh;
    margin-right: 10px;
    float: right;
    h1 {
      font-family: "madre-script";
      font-size: 50px;
      line-height: 56px;
      text-align: center;
      color: #333;
      text-shadow: white 0px 0px 10px;
    }
  }
  .countdown {
    margin-top: 50px;
    text-align: center;
    text-shadow: white 0px 0px 10px;
  }
</style>
