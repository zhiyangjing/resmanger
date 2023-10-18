<template>
  <div class="whole">
    <div class="card">
      <img src="../../static/user/avator.svg" class="avator">
      <div class="right-part">
        <div class="name">
          昵称: {{ userName }}
        </div>
        <div class="user-id">
          ID: {{ userId }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
// const userName = "asdf"
const userName = ref("用户昵称")
const userId = ref("123456@tiaozhan")

</script>


<style scoped>
:root {
  --radius:60px;
}
.whole {
  /* border:solid red 1px; */
  display: flex;
  justify-content: center;
  align-items: center;
}

.card {
  height:100px;
  width:90vw;
  /* border:solid blue 1px; */
  margin-top: 20px;
  display: flex;
  align-items: center;
  border:1px var(--theme-grey-light) solid;
  border-radius:10px;
  box-shadow: 0 0 15px var(--theme-grey-moderate);
}
.avator {
  margin-left:20px;
  height:var(--radius);
  width:var(--radius);
  /* border-radius:50%; */
  /* border:solid 1px orange; */
}

.right-part {
  width:60vw;
  height:calc(100% - 20px);
  margin-left:10px;
  /* border:solid 1px orange; */
  display:flex;
  flex-direction: column;
  justify-content: space-around;
}

.name {
  font-size: 23px;
  font-weight: 900;
  margin-left:20px;
  /* border:solid 1px red; */
}

.user-id {
  color:var(--theme-grey);
  margin-left:20px;
}
</style>

