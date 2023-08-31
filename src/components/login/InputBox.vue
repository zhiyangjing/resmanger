<script setup lang="ts">
import { onMounted, ref} from 'vue'
const account = ref("")
const password = ref("")
const inputstyle1 = ref("solid var(--theme-grey) 1px")
const inputstyle2 = ref("solid var(--theme-grey) 1px")
const visiable = ref(false)
const ispassword = ref("password")
const isFoucs = ref(false)
const isChecked = ref(false)

function getfocus (index : number){
  if (index == 0) inputstyle1.value = "solid var(--theme-color) 1px;"
  else if (index == 1) inputstyle2.value = "solid var(--theme-color) 1px;"
  //console.log("focus",index)
}

function getblur(index : number){
  if (index == 0) inputstyle1.value = "solid var(--theme-grey) 1px;"
  else if (index == 1){
    inputstyle2.value = "solid var(--theme-grey) 1px;"
    isFoucs.value = false;
  }
  //console.log("blur",index)
}

function changevisable(){
  isFoucs.value = true
  visiable.value = !visiable.value
  if (visiable.value) {ispassword.value="none"}
  else {ispassword.value="password"}
}

function onChange(){
  isChecked.value = !isChecked.value
  // console.log(isChecked)
}

function atinput(){

}

function getLogin () {
  uni.navigateTo({
    url: '/pages/index/Index'
  })
  console.log("change to homepage")
}


</script>

<template>
  <div class="whole">
    <div class="info account">
      <van-icon name="wap-home" class="input-icon" color="#9a9a9a"/>
      <!-- <image src="../static/login/home.svg" class="input-icon"/> -->
      <input
        v-model="account"
        placeholder="请输入账号"
        placeholder-class="input-placeholder"
        @focus="getfocus(0)"
        @blur="getblur(0)"
        @input="atinput()"
      />
    </div>
    <div class="info password">
      <van-icon name="lock" class="input-icon" color="#9a9a9a"/>
      <!-- <image src="../static/login/lock.svg" class="input-icon"/> -->
      <input
        v-model="password"
        :type="ispassword"
        placeholder="请输入密码"
        placeholder-class="input-placeholder"
        :focus="isFoucs"
        @focus="getfocus(1)"
        @blur="getblur(1)"
        @input="atinput()"
      />
      <van-icon name="eye-o" class="input-icon" v-if="!visiable" @click="changevisable()" color="#9a9a9a"/>
      <van-icon name="closed-eye" class="input-icon" v-if="visiable" @click="changevisable()" color="#9a9a9a"/>

      <!-- <image src="../static/login/eye.svg" class="input-icon" v-if="!visiable" @click="changevisable()"/> -->
      <!-- <image src="../static/login/eye-close.svg" class="input-icon" v-if="visiable" @click="changevisable()"/> -->
    </div>
    <div class="choice">
      <van-checkbox 
        :value="isChecked" 
        shape="square" 
        @change="onChange()"
        checked-color="grey"
        icon-size="13px" 
        class="check-box"
      >
        记住密码
      </van-checkbox>

      <div class="forget">
          忘记密码
      </div>
    </div>
    
        
    <div class="login-btn" @click="getLogin()">
      登录
    </div>
  </div>
</template>


<style scoped>
.whole {
  height:350px;
  width:100vw;
  /* border:2px red solid; */
  display: flex;
  flex-direction: column;
  align-items: center;
}

.info {
  height: var(--input-box-height);
  width:68vw;
  margin-top: 20px;
  display: flex;
  align-items: center;
}

input {
  height:inherit;
  color:#4e4e4e;
}

.account {
  border-radius: 17px;
  border: v-bind("inputstyle1") !important;
}
.password {
  border-radius: 17px;
  border: v-bind("inputstyle2");
}

.input-icon {
  height:var(--input-box-border-radius);
  width:var(--input-box-border-radius);
  margin-left: 14px;
  margin-right: 14px;
}
.login-btn {
  height: var(--input-box-height);
  width:68vw;
  margin-top: 5px;
  display: flex;
  align-items: center;
  background-color: var(--theme-color-light);
  border:solid #9a9a9a9a 1px;
  border-radius:var(--input-box-border-radius);
  justify-content: center;
  transition: 80ms;
}

.login-btn:active {
  background-color: var(--theme-color);
}

.choice {
  margin-top:8px;
  margin-bottom:4px;
  height:20px;
  width:70vw;
  /* border:solid red 2px; */
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}

.forget {
  display: flex;
  position: relative;
  right:0px;
  font-size: 13px;
  color:var(--theme-grey)
}

#to-rem {
  height:10px;
  width:10px;
  background-color: black;
}

.check-box {
  font-size: 13px;
}
</style>

  <!-- name: "Login",
  props: {},
  computed: {},
  methods: {},
  watch: {},
  mounted() {},
  beforeUpdate() {},
  updated() {},
  activated() {},
  deactivated() {},
  beforeDestroy() {}, -->
