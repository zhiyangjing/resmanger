<script setup lang="ts">
import { ref } from 'vue'
// import DeviceCard from './DeviceCard.vue';
import HistoryCard from './HistoryCard.vue'
const isAall = ref(0)

function onChange(){

}
</script>

<template>
  <div class="whole">
    <van-tabs type="card" :active="isAall" @change="onChange()" color="#72a2eb">
      <div class="tab-wrapper">
        <van-tab title="个人借还记录">
          <HistoryCard>

          </HistoryCard>
          <HistoryCard>

          </HistoryCard>
          <HistoryCard>

          </HistoryCard>
          <HistoryCard>

          </HistoryCard>
        </van-tab>
      </div>
      <div class="tab-wrapper">
        <van-tab title="全部借还记录">Second</van-tab>
      </div>
    </van-tabs>
  </div>
</template>


<style scoped>

.whole {
  margin-top:30px;
  /* border:solid red 1px; */
}
.history-bar {
  /* border:solid 1px red; */
  height:100px;
}

.tab-wrapper {
  margin-top:30px;
}
</style>