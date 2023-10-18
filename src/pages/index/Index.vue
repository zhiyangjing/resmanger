<template>
  <HomePage v-if="active == 0">

  </HomePage>
  <UserPage v-if="active == 3">

  </UserPage>
  <div class="homepage" @click="goback()">back</div>
  <van-tabbar :active="active" @change="onChange" class="tabbar">
    <van-tabbar-item icon="wap-home-o">首页</van-tabbar-item>
    <van-tabbar-item icon="records">物资管理</van-tabbar-item>
    <van-tabbar-item icon="shopping-cart-o">设备车</van-tabbar-item>
    <van-tabbar-item icon="user-o">个人中心</van-tabbar-item>
  </van-tabbar>
  <div class="stairs">

  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import HomePage from './HomePage.vue';
import UserPage from './UserPage.vue';
const active = ref(0)


function onChange(event : any){
  active.value = event.detail
  // console.log(event.detail)
}

function goback(){
  uni.redirectTo({
    url:"/pages/login/Login"
  })
}

</script>

<style scoped>
.stairs {
  height:200rpx;
}
.tabbar {
  z-index: 10;
}
</style>