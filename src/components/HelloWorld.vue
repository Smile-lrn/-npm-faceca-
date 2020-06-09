<template>
  <div>
    {{ msg }}
    <face :activename="activeName" :isrest='isRest' @restActive='restactive' @responseFun='responseFun' ></face>
    <button id="facelogin" @click="faceLogin">人脸登录</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: '',
      activeName: '',
      isRest:false
    };
  },
  methods: {
    // 进入人脸识别页面
    faceLogin() {
      this.activeName = 'active';
    },
    // 重置插件中的数据
    restactive(val){
      this.activeName = val
      this.isRest = false;
    },
    responseFun(data){
      // 活体检测后的图片
       console.log(data)
       setTimeout(()=>{
         this.isRest = true;
       },1000)
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
