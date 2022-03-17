<template>
  <div class="">
    <div class=" ">
      <div class="flex justify-center text-8xl text-blue-600 mb-8">Ngày 26 tháng 6 năm 2020 </div>
      <div class="flex justify-center text-7xl text-pink-500">9 giờ 30 phút 00 giây</div>
    </div>
    <div class="flex justify-between m-auto w-1/2 mt-8">
      <button class="border-2 hover:text-white hover:bg-red-600 border-red-600 py-2 px-4 text-red-600 rounded-2xl cursor-pointer " @click="ishange(1)">Năm</button>
      <button class="border-2 hover:text-white hover:bg-yellow-500 py-2 px-4  border-yellow-500 text-yellow-500 rounded-2xl cursor-pointer" @click="ishange(2)">Tháng</button>
      <button class="border-2 hover:text-white hover:bg-yellow-200 py-2 px-4 border-yellow-200 text-yellow-200 rounded-2xl cursor-pointer" @click="ishange(3)">Ngày</button>
      <button class="border-2 hover:text-white hover:bg-green-600 py-2 px-4 border-green-600 text-green-600 rounded-2xl cursor-pointer" @click="ishange(4)">Giờ</button>
      <button class="border-2 hover:text-white hover:bg-blue-700 py-2 px-4 border-blue-700 text-blue-700 rounded-2xl cursor-pointer" @click="ishange(5)">Phút</button>
      <button class="border-2 hover:text-white hover:bg-purple-700 py-2 px-4 border-purple-700 text-purple-700 rounded-2xl cursor-pointer" @click="ishange(6)">Giây</button>
    </div>
    <div class="flex justify-center mx-auto m-auto  mt-8" v-if="love=='26'">
    <div class="border-2 hover:text-white hover:bg-yellow-500 py-2 px-4  border-yellow-500 text-yellow-500 rounded-2xl cursor-pointer" @click="ishange(7)" >
      chúc mừng ngày cảu 2 đứa
    </div>
    </div>
  </div>
</template>

<script>
import moment from 'moment'

export default {

  data(){
    return{
      love:0
    }
  },
  created(){
    this.moment = moment;
    this.love = moment("Thu Mar 17 2022 23:59:25 GMT+0700").format("DD")
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