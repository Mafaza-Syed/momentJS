<template>
  <div class="container">
    <div class="form-group">
      <label for="dt1">Choose Date 1</label>
      <input type="date" name="dt1" v-model="dt1" class="form-control" />
    </div>
    <div class="form-group">
      <label for="dt2">Choose Date 2</label>
      <input type="date" name="dt2" v-model="dt2" class="form-control" />
    </div>

    <input
      type="submit"
      @click="calculate()"
      class="btn btn-primary"
      value="Find Difference"
    />
    <p v-if="!empty">Difference in months is :{{result}} months </p>
  </div>
</template>
<script>
var moment = require("moment");
export default {
  data() {
    return {
      moment: moment,
      dt1: "",
      dt2: "",
      empty: true,
      result: '',
    };
  },
  methods: {
    calculate() {
      this.empty = false;

      // moment.sub(this.dt1, this.dt2, 'months');
      var a = moment(this.dt1);
      console.log(a);
      var b = moment(this.dt2);
      console.log(b);
       var c = a.diff(b, "months");
       console.log(c);
      this.result= c;
    }
  }
};
</script>
<style></style>

// methods:{ // diff_months(dt2, dt1){ // var diff =(dt2.getTime() -
dt1.getTime()) / 1000; // diff /= (60 * 60 * 24 * 7 * 4); // return
Math.abs(Math.round(diff)); // this.result(); // }, // result(){ // dt1 = new
Date(this.dt1), // dt2 = new Date(this.dt2), //
console.log(diff_months(this.dt1, this.dt2)), // dt1 = new Date("June 13, 2014
08:11:00"), // dt2 = new Date("October 19, 2014 11:13:00"), //
console.log(diff_months(dt1, dt2)); // } // }
