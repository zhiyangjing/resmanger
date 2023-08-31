<template>
  <div class="whole">
    <img src="../../static/temp/camera.jpg" class="picture" mode="aspectFit">
    <div class="lower">
      <div class="title">
        佳能相机
      </div>
      <div class="subtitle">
        高画质专业操控感2420w像素
      </div>
    </div>
  </div>  
</template>

<script setup lang="ts">

</script>

<style scoped>
.whole {
  /* border:solid red 1px; */
  height:200px;
  /* margin-left:4px;
  margin-right:4px; */
  width:42vw;
  box-shadow: 0px 0px 15px var(--theme-grey-moderate);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.picture {
  height:140px;
  width:42vw;
  /* border:solid red 1px; */
}

.lower {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width:25vw;
  /* border:solid red 1px; */
}
.title {
  font-weight: 900;
  font-size: 15px;
}
.subtitle {
  margin-top:6px;
  font-weight: 400;
  font-size: 10px;
  color:var(--theme-grey);
  text-align:center;
}
</style>