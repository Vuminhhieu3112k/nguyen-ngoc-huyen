<template>
  <div class="">
      <div class="text-center m-auto w-3/4 text-6xl text-blue-600 mb-8">Số giờ yêu nhau có tăng thêm nữa thì anh vẫn thấy không đủ vậy nên...</div>
      <div class="text-center m-auto w-3/4 text-6xl text-blue-600 mb-8" v-if="text">Làm vợ anh nhé để biến nó thàng vô cùng</div>
      <div class="flex justify-center text-6xl text-blue-600 mb-8">{{love}} Giờ bên nhau</div>
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
            text: false,
            today: moment("Thu Mar 17 2022 23:59:25 GMT+0700").format("MM/DD/YYYY/HH/mm"),
                
        }
    },
    created () {
    this.moment = moment;
    this.inDays(this.today,"06/26/2020/21/30")

    setInterval(()=>{
       this.today= moment("Thu Mar 17 2022 23:59:25 GMT+0700").format("MM/DD/YYYY/HH/mm")
    },1000)
    setTimeout(()=>{
        this.text = true
    },5000)
    },
    methods:{
        inDays(time1, time2){
            var str1= time1.split('/');
            var str2= time2.split('/');
            
            //                yyyy   , mm       , dd      
            var t1 = new Date(str1[2], str1[0]-1, str1[1], str1[3], str1[4]);
            var t2 = new Date(str2[2], str2[0]-1, str2[1], str2[3], str2[4]);
            console.log(t1,t2);
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
             this.love= Math.floor(diffH);
        },
                ishange(data){
      this.$emit('ishange',data)
    }
    },
    watch:{
      today: {
      handler: function (val) {
          this.inDays(val,"06/26/2020/21/30")
      },
      deep: true,
    },
  }
}
</script>

<style>

</style>