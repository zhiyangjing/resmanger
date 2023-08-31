<template>
  <div class="container">
    <van-tabs :active="activateGroup" @change="changeGroup" 
      color="var(--theme-color-moderate)">
      <van-tab title="全部设备">
        <div class="item-container">
          <DeviceCard class="item" :itemNums="12">
            <template v-slot:item-name>
              相机
            </template>
          </DeviceCard>
          <DeviceCard class="item" :itemNums="11">
            <template v-slot:item-name>
              相机
            </template>
          </DeviceCard>
          <DeviceCard class="item" :itemNums="12">
            <template v-slot:item-name>
              相机
            </template>
          </DeviceCard>
          <DeviceCard class="item" :itemNums="12">
            <template v-slot:item-name>
              相机
            </template>
          </DeviceCard>
          <DeviceCard class="item" :itemNums="12">
            <template v-slot:item-name>
              相机
            </template>
          </DeviceCard>
          <DeviceCard class="item" :itemNums="12">
            <template v-slot:item-name>
              相机
            </template>
          </DeviceCard>
        </div>
      </van-tab>
      <van-tab title="相机系列" class="item-container"></van-tab>
      <van-tab title="常用设备" class="item-container"></van-tab>
      <van-tab title="桌椅设备" class="item-container"></van-tab>
    </van-tabs>
    <div class="more">查看更多>></div>
  </div>
</template>


<script setup lang="ts">
import DeviceCard from './DeviceCard.vue';
import { ref } from 'vue';
const activateGroup = ref(0)


function changeGroup(event : any){
  activateGroup.value = event.detail.index
}


</script>

<style scoped>
.container {
  /* height:2000rpx; */
  display: grid;
}
.item {

}

.item-container {
  display: grid;
  grid-template-columns: auto auto;
  /* grid-template-rows: auto auto auto auto; */
}
.tmp {
  background-color: red;
  width:100px;
  height:200px;
  margin:10px;
}
.more {
  margin-top:10px;
  background-color: var(--theme-color-pale);
  height:33px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: bold;
  color: var(--theme-color-light)
}
</style>