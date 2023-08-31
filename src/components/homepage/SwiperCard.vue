<template>
  <div class="main">
    <div class="left-part">
      <div class="title">
        <slot name="title">
          物资借阅须知
        </slot>
      </div>

      <div class="more">
        <slot name="more">
          查看详情
        </slot>
      </div>
    </div>
    <div class="right-part">
      <slot>
        <image src="../../static/swiper/information.svg" class="icon"/>
      </slot>
    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
.main {
  height:337rpx;
  /* border:red solid 1px; */
  background: linear-gradient(310deg,var(--theme-color),var(--theme-color-light));
  display: flex;
  flex-direction: row;
  justify-content: space-around;  
  border-radius: 20rpx;
}
.left-part {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width:40%;
  /* border:blue solid 1px; */
}

.title {
  font-size: 38rpx;
  font-weight: 1000;
  color:white;
  /* border:red solid 1px; */
}
.right-part {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width:40%;
  /* border:blue solid 1px; */
}
.right-part > image{
  /* border:solid aqua 1px; */
  width:250rpx;
}
.more {
  height:50rpx;
  width:120rpx;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--theme-color-moderate);
  font-size: 20rpx;
  color:white;
  font-weight: 600;
  border-radius: 10rpx;
  /* border:solid red 1px; */
}
</style>