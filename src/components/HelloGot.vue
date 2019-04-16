<template>
  <div class="hello">
    <h1>
      {{
        `Game of Thrones is on in ${timerObject[0]} days, ${
          timerObject[1]
        } hours, ${timerObject[2]} minutes, and ${timerObject[3]} seconds`
      }}
    </h1>
  </div>
</template>

<script>
export default {
  name: "HelloGot",
  props: {
    secondsTillGotStarts: Number
  },
  computed: {
    timerObject: function() {
      const daysTillGot = Math.floor(
        this.secondsTillGotStarts / (60 * 60 * 24)
      );
      const hoursInRemainder = Math.floor(
        (this.secondsTillGotStarts % (60 * 60 * 24)) / (60 * 60)
      );
      const minutesInRemainder = Math.floor(
        (this.secondsTillGotStarts % (60 * 60)) / 60
      );
      const secondsInRemainder = Math.floor(this.secondsTillGotStarts % 60);
      const timerObject = [
        daysTillGot, // days
        hoursInRemainder,
        minutesInRemainder, // minutes
        secondsInRemainder // seconds
      ];
      return timerObject;
    }
  }
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
