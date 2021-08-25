<template>
  <div class="">
    <div class="xien  mb-8 bg-white rounded-2xl p-4 cursor-pointer" @click="ishange(0)">
       <img src='../../assets/img/bo-hoa-do-an-giadinhmoivn-2-1115.jpg' width="500"  alt="">
       <div class="mt-4 text-center">anh yêu em</div>

    </div>
  </div>
</template>

<script>

export default {
  methods:{
    ishange(data){
      this.$emit('ishange',data)
    }
  }
};
</script>

<style  scoped>

</style>