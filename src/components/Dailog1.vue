<template>
  <div class="bg-black h-screen flex justify-center items-center ">
      <div class=" bg-white w-82  rounded-xl p-6">
          <div  class="">bé ơi </div>
            <div  class="">chắc bé cũng biết nay là ngày gì</div>
            <div  class="">anh có món quà tặng bé để bé ko còn cần tính ngày mình yêu nữa</div>
            <div class="flex justify-around mt-4">
                <button  @click="dailogOff" class="btn mr-8 text-2xl py-4 px-6 rounded-xl text-white font-bold bg-green-600">ok</button>
            </div>
      </div>
  </div>
</template>

<script>
export default {
  methods:{
    dailogOff(){
      this.$emit('dailogOff')
    }
  }
}
</script>

<style>

</style>