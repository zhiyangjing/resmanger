<template>
  <view class="whole">
    <view id="bkg_color">
      <image src="../../static/login/homepage.svg" id="bkg-img"/>
      <image src="../../static/white.png" id="logo"/>
      <view id="login">
        <InputBox>
          gsdfg
        </InputBox>
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import InputBox from '../../components/login/InputBox.vue'

function test(){
  console.log("right here")
  uni.navigateTo({
    url: '/pages/index/Index'
  })
}


</script>

<style scoped>
.whole {
  height: 100vh;
  width:100vw;
  display: flex;
}

.login-part {
  position: fixed;
  bottom:20vh;
}
#logo {
  position: absolute;
  margin:40px;
  width:170px;
  height:60px;
}

#bkg_color {
  background: linear-gradient(0deg,rgb(255,255,255),var(--theme-color));
  height: 80vh;
  width:100vw;
  display: flex;
  justify-content: center;
}

#bkg-img {
  position: absolute;
  top:15vh;
  height:40vh;
  width:40vh;
}

#login {
  position: absolute;
  bottom: 0;
}
</style>