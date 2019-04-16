<template>
  <div id="app">
    <img alt="Game of Thrones gif" src="./assets/success-logo.gif" />
    <HelloGot :secondsTillGotStarts="secondsTillGotStarts" />
  </div>
</template>

<script>
import HelloGot from "./components/HelloGot.vue";
import setDay from "date-fns/set_day";
import differenceInMilliseconds from "date-fns/difference_in_milliseconds";

export default {
  name: "app",
  data: function() {
    return {
      secondsTillGotStarts: 0
    };
  },
  methods: {
    calculateGotTimer: function() {
      const today = new Date();
      const nextGotStarts = new Date(
        Date.UTC(
          today.getFullYear(),
          today.getMonth(),
          setDay(today, 7).getDate() + 1,
          1,
          0,
          0
        )
      );
      this.secondsTillGotStarts =
        -differenceInMilliseconds(today, nextGotStarts) / 1000;
      setTimeout(this.calculateGotTimer, 1000);
    }
  },
  created: function() {
    this.calculateGotTimer();
  },
  components: {
    HelloGot
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
  background-color: black;
}
</style>
