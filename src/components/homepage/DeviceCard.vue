<template>
  <div class="whole">
    <div class="item-image-container">
      <img src="../../static/temp/camera.jpg" class="item-image">
    </div>
    <div class="item-info">
      <div class="item-name">
        <slot name="item-name">
        </slot>
      </div>

      <div class="item-nums">
        剩余数量:&nbsp; {{ itemNums }}        
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { onMounted,defineProps } from 'vue'
const props = defineProps({
  itemNums: Number
})

const itemNums = props.itemNums


</script>

<style scoped>
:root {
  --image-height:67%;
}
.whole {
  display: flex;
  /* justify-content: center; */
  align-items: center;
  margin:8px;
  height:180px;
  width:auto;
  flex-direction: column;
}

.item-image-container {
  height:var(--image-height);
  width:100%;
  background-color: var(--theme-color-pale);
}

.item-image {
  height:100%;
  width:100%;
  object-fit: contain;
}
.item-info {
  height:calc(100% - var(--image-height));
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.item-name {
  font-size: large;
  font-weight: bold;
  margin-top: 5px;
}

.item-nums {
  font-size: small;
  font-weight: light;
  color: grey;
}
</style>