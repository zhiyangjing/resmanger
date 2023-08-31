<template>
  <div class="whole">
    <div class="pit">
      <!-- 2023 -->
    </div>
    <div class="right">
      <div class="picutre">
        <img src="../../static/temp/drone.jpg" class="pic" mode="aspectFit"/>
      </div>
      <div class="info">
        <div class="title">
          无人机
        </div>
        <div class="subtitle">
          大疆精灵4pro
        </div>
        <div class="time">
          2023-8-2
        </div>
        <button class="button">
          查看详情
        </button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

</script>


<style scoped>
:root {
  --radius:45px;
}
.whole {
  height:180px;
  /* border:solid 1px red; */
  display: flex;
  flex-direction: row;
}

.pit {
  height:var(--radius);
  width:var(--radius);
  background-color:var(--theme-grey-light);
  border-radius: 50%;
  transform: translate(calc(var(--radius) / 2),30px);
  display: flex;
  justify-content: center;
  align-items: center;
}
.pit::before{
  content:"2023";
  height:calc(var(--radius) - 8px);
  width:calc(var(--radius) - 8px);
  background-color:rgba(255, 255, 255, 0);
  /* background-color: black; */
  border:2px solid white;
  border-radius: 50%;
  display:flex;
  justify-content: center;
  align-items: center;
  font-size: small;
  font-weight: 800;
}

.right {
  border-left:1px dashed blue;
  display: flex;
  flex-direction: row;
}

.picutre {
  margin-left:calc(var(--radius) / 2 + 10px);
  background-color:var(--theme-color-pale);
  display: flex;
  justify-content: center;
  align-items: center;
}
.pic {
  height:140px;
  width: 140px;
}
.info {
  margin-left:20px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
.title {
  font-weight: 1000;
  font-size: 20px;
  margin-top:20px;
}
.subtitle{
  margin-bottom:7px;
  font-weight: 500;
  font-size:15px;
  color:var(--theme-grey);
}
.time {
  margin-top:7px;
  font-weight: 500;
  font-size:15px;
  color:var(--theme-grey);
}

.button {
  background-color: var(--theme-color-light);
  margin-bottom:0px;
  color:white;
  display: flex;
  justify-content:center;
  align-items: center;
  height:26px;
  border-radius: 5px;
  font-size: 14px;
}

</style>