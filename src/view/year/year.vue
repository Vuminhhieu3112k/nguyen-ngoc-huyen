<template>
  <div class="">
    <div class="flex justify-center text-8xl text-blue-600 mb-8">
      Em biết không chúng ta đã bên nhau
    </div>
    <div class="flex justify-center text-8xl text-blue-600 mb-8">
      {{ yaers }} năm, {{ moth }} tháng, {{ day }} ngày
    </div>
    <div class="text-center flex justify-center mt-4 cursor-pointer">
      <fa icon="heart" class="mx-auto text-6xl text-red-600" @click="ishange(0)"/>
    </div>
  </div>
</template>

<script>
import moment from "moment";

export default {
  data() {
    return {
      yaers: 0,
      moth: 0,
      love: 0,
      day: 0,
    };
  },
  created() {
    this.moment = moment;
    this.love = moment()
      .add(-2020, "y")
      .add(-6, "months")
      .add(-26, "d")
      .add(-21, "hours")
      .format("DD MM YYYY hh:mm:ss");
    this.yaers = this.love.substring(8, 10);
    this.moth = this.love.substring(3, 5);
    this.day = this.love.substring(0, 2);
  },
  methods:{
    ishange(data){
      this.$emit('ishange',data)
    }
  }
};
</script>

<style>
</style>