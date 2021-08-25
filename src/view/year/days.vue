<template>
  <div class="">
      <div class="text-center m-auto w-3/4 text-6xl text-blue-600 mb-8">Số ngày chúng ta yêu nhau càng tăng lên thì tình cảm đôi ta lại bền chặt thêm </div>
      <div class="flex justify-center text-6xl text-blue-600 mb-8">{{inDays(today,"06/26/2020")}} Ngày bên nhau</div>
          <div class="text-center flex justify-center mt-4 cursor-pointer">
      <fa icon="heart" class="mx-auto text-6xl text-red-600" @click="ishange(0)"/>
    </div>
  </div>
</template>

<script>
import moment from 'moment'

export default {
    data(){
        return{
            love:0,
            yaers:0,
            moth:0,
            day:0,
            today: 0,
            today1: new Date(2021,8,26,21,30)

        }
    },
    created () {
    this.moment = moment;

   this.today =moment().format("MM/DD/YYYY")

    },
    methods:{
        inDays(time1, time2){
            var str1= time1.split('/');
            var str2= time2.split('/');
            
            //                yyyy   , mm       , dd
            var t1 = new Date(str1[2], str1[0]-1, str1[1]);
            var t2 = new Date(str2[2], str2[0]-1, str2[1]);
            
            var diffMS = t1 - t2;    
            console.log(diffMS + ' ms');
            
            var diffS = diffMS / 1000;    
            console.log(diffS + ' ');
            
            var diffM = diffS / 60;
            console.log(diffM + ' minutes');
            
            var diffH = diffM / 60;
            console.log(diffH + ' hours');
            
            var diffD = diffH / 24;
            console.log(diffD + ' days');
            return diffD;
        },
                ishange(data){
      this.$emit('ishange',data)
    }
    }
}
</script>

<style>

</style>