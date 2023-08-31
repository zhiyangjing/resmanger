<template>
  <div class="whole">
    <image src="../../static/orange.png" class="logo" :class="['fade',{'fade-out': isFadingOut}]" v-show="!isSearching" />
    <div class="search-wraper">
      <div class="search-width">
      <van-search 
        :value="searchValue" 
        placeholder="请输入设备名称" 
        @focus="changeState(1)" 
        @blur="changeState(0)" 
      />
      </div>
    </div>
    <div class="lower-part">
      <view class="uni-margin-wrap">
        <swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
          :duration="duration">
          <swiper-item>
            <SwiperCard>
            </SwiperCard>
          </swiper-item>
          <swiper-item>
            <SwiperCard>
            </SwiperCard>
          </swiper-item>
          <swiper-item>
            <SwiperCard>
            </SwiperCard>
          </swiper-item>
        </swiper>
      </view>
      <!-- <div class="test" :class="['fade',{'fade-out': isFadingOut}]" v-show="!isSearching" >
        THIS IS TEST PART
      </div> -->
      <div class="device-wrapper">
        
        <Devices>

        </Devices>
      </div>
      <div class="history-wrapper">
        <History>
          
        </History>
      </div>
      <div class="alldevices-wrapper">
        <AllDevices>

        </AllDevices>
      </div>
      <div class="footer">
        <div class="end">tiaozhan公司版权所有</div>
        <div>'tiaozhan'&ensp;&ensp;&ensp;'挑战网'&ensp;&ensp;&ensp;'tenzor'</div>
      </div>      
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import SwiperCard from '@/components/homepage/SwiperCard.vue';
import Devices from '@/components/homepage/Devices.vue';
import History from '@/components/homepage/History.vue';
import AllDevices from '@/components/homepage/AllDevices.vue';
const searchValue = ref("")
const isSearching = ref(false)
const isFadingOut = ref(false)
const changeTime = 200
const changeTimestyle = changeTime + "ms"
const indicatorDots=true
const autoplay=true
const interval=2000
const duration=500



function changeState(choice : number){
  if (choice == 1) {
    isFadingOut.value = true
    console.log(isSearching.value)
    setTimeout(()=>{
      isSearching.value = true
      console.log("begin fade")
    },changeTime)
  } else if (choice == 0) {
    isSearching.value = false
    setTimeout(()=>{
      isFadingOut.value = false
    },1)
  }
  // toggleVisible()
}

</script>

<style scoped>
.whole {
  display: flex;
  flex-direction: column;
}
.logo {
  width:160px;
  height:58px;
  margin-left: 10px;
  margin-top: 10px;
  /* border:red 1px solid; */
}

.logo-wraper {
  width:100vw;
  height:0px;
  /* border:1px blue solid; */
}

.test {
  height:50vh;
  width:95vw;
  /* border: red 1px solid; */
}

.search-wraper {
  width:100vw;
  display: flex;
  justify-content: center;
  /* border:1px blue solid; */
}

.search-width {
  width:96vw;
}

.lower-part {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.fade {
  transition: opacity v-bind(changeTimestyle),height v-bind(changeTimestyle) ,margin v-bind(changeTimestyle); /*设置过渡效果的持续时间 
  /* transition: height v-bind(changeTimestyle); */
}

.fade-out {
  opacity: 0; /* 消失时的透明度 */
  height:0vh;
  margin:0;
}
.uni-margin-wrap {
  width: 690rpx;
  width: 90vw;
}
.swiper {
  height: 340rpx;
}
.swiper-item {
  display: block;
  height: 340rpx;
  line-height: 300rpx;
  text-align: center;
}

.device-wrapper {
  width:90vw;
  /* border:solid 1px red; */
}
.history-wrapper {
  width:100vw;
  /* border:solid 1px red; */
}
.alldevices-wrapper {
  width:100vw;
}

.footer {
  margin-top:30px;
  width:100vw;
  height:80px;
  background-color: rgb(47, 47, 47);
  color:var(--theme-grey);
  display: flex;
  text-align: center;
  justify-content: center;
  flex-direction: column;
}

.end {
  margin-bottom:4px;
}
</style>