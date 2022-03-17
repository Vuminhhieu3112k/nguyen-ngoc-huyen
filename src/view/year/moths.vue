<template>
  <div class="">
      <div class="flex justify-center text-6xl text-blue-600 mb-8">Mỗi tháng chúng ta lại có 1 kỉ niệm vào ngày 26</div>
      <div class="flex justify-center text-6xl text-blue-600 mb-8">Ngày 26 là ngày 2 đứa bắt đầu</div>

      <div class="flex justify-center text-6xl text-blue-600 mb-8">vậy là chúng ta đã chúc nhau {{moth}} lần tượng trưng cho {{moth}} tháng</div>
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
            moth:0
        }
    },
    created () {
    this.moment = moment;
    this.love = moment("Thu Mar 17 2022 23:59:25 GMT+0700").add(-2020,'y').add(-6,'months').add(-26,'d').add(-21,'hours').format("DD MM YYYY hh:mm:ss")
    this.yaers =this.love.substring(8,10)
    this.moth= parseInt(this.love.substring(3,5))  + parseInt(this.love.substring(8,10))*12


    },
    methods:{
        ishange(data){
      this.$emit('ishange',data)
    }
    }
}
</script>

<style>

</style>