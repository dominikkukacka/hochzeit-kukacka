<template>
  <div>
    <div class="block">
      <p class="digit">
        <span>{{ days | two_digits }}</span> Tage
      </p>
    </div>
    <div class="block">
      <p class="digit">
        <span>{{ hours | two_digits }}</span> Stunden
      </p>
    </div>
    <div class="block">
      <p class="digit">
        <span>{{ minutes | two_digits }}</span> Minuten
      </p>
    </div>
    <div class="block">
      <p class="digit">
        <span class="seconds">{{ seconds | two_digits }}</span> Sekunden
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      date: null
    },

    data() {
      return {
        now: Math.trunc((new Date()).getTime() / 1000),
        event: this.date
      }
    },

    computed: {
      calculatedDate() {
        this.event = Math.trunc(Date.parse(this.event) / 1000)
        return this.event
      },
      seconds() {
        return (this.calculatedDate - this.now) % 60
      },
      minutes() {
        return Math.trunc((this.calculatedDate - this.now) / 60) % 60
      },
      hours() {
        return Math.trunc((this.calculatedDate - this.now) / 60 / 60) % 24
      },
      days() {
        return Math.trunc((this.calculatedDate - this.now) / 60 / 60 / 24)
      }
    },

    mounted() {
      window.setInterval(() => {
        this.now = Math.trunc((new Date()).getTime() / 1000)
      }, 1000)
    }
  }
</script>

<style lang="scss">
  .block {
    font-family: "museo";
    font-weight: 100;
    display: inline;
    font-size: 30px;
    color: #333;
    .text {
      display: inline;
    }
    .digit {
      display: inline;
      margin: 5px;
    }
  }
</style>
