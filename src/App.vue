<template>
  <div class="app h-screen">
    <Dailog1 v-if="hiddenDailog"   @dailogOff="dailogOff"/>
    <div class="flex items-center h-full justify-center">
      <HomePage @ishange="ishange" v-if="select==0"/>
      <Year @ishange="ishange" v-if="select==1"/>
      <Moths  @ishange="ishange" v-if="select==2"/>
      <Days @ishange="ishange" v-if="select==3"/>
      <Hours @ishange="ishange" v-if="select==4"/>
      <Minutes @ishange="ishange" v-if="select==5"/>
      <Seconds @ishange="ishange" v-if="select==6"/>
      <Xien @ishange="ishange" v-if="select==7"/>
    </div>
  </div>
</template>

<script>
import HomePage from "./view/index.vue";
import Dailog1 from './components/Dailog1.vue'
import moment from "moment";
import Year from "./view/year/year.vue";
import Moths from './view/year/moths.vue';
import Hours from './view/year/hours.vue';
import Minutes from './view/year/minutes.vue';
import Seconds from './view/year/seconds.vue';
import Days from './view/year/days.vue';
import Xien from './view/year/xien.vue'

export default {
  data() {
    return {
      select:0,
      hiddenDailog: true,
    };
  },
  created: function () {
    this.moment = moment;
  },
  components: {
    Dailog1,
    HomePage,
    Year,
    Moths ,
    Hours,
    Minutes,
    Seconds,
    Days,
    Xien
  },
  methods: {
    dailogOff() {
      this.hiddenDailog = false;
    },
    ishange(data){
      this.select=data
    }
  },
};
</script>

<style>
.app {
  background: url("./assets/img/215339396_790468431664195_1225113675248070019_n.jpg");
  background-size: cover; /* <------ */
  background-repeat: no-repeat;
  background-position: center center;
  font-family: "Style Script", cursive;
}
</style>