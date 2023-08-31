<template>
  <div class="whole">
    <div class="upper">
      <div class="headline">
        全部物资
      </div>
      <div class="bar">
      </div>
      <div class="subheadline">
        你想要的物资这里都有
      </div>
      <div class="items">
        <AllCard>

        </AllCard>
        <AllCard>

        </AllCard>
        <AllCard>

        </AllCard>
        <AllCard>

        </AllCard>
        <AllCard>

        </AllCard>
        <AllCard>

        </AllCard>
      </div>
    </div>
  </div>
  
</template>

<script setup lang="ts">
import AllCard from './AllCard.vue';

</script>

<style scoped>
:root {
  --headline-height:30px;
}
.whole {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.upper {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.headline {
  /* border:1px blue solid; */
  margin-top:20px;
  display: flex;
  justify-content: center;
  align-items: center; 
  font-size: 25px;
  font-weight: 900;
  height:var(--headline-height);
  background-color: white;
  z-index:1;
  width:30vw;
}

.bar {
  background-color: var(--theme-color-light);
  height:3px;
  width:36vw;
  transform:translateY(-15px);
  /* transform:translateY(-20px); */
  z-index:0;
}

.subheadline {
  font-weight: 400;
  font-size: small;
  color:var(--theme-grey)
}

.items {
  margin-top:20px;
  display: grid;
  grid-template-columns: auto auto;
  gap:8px 8px;
}
</style>