<template>
  <div class="wrapper">
    <div class="container --el-box-shadow-lighter">
      <h2 style="margin-top: 6vh;" class="text_center">账号登录</h2>
      <div class="loginBox">
        <el-form size="large" :model="formInline">
          <el-form-item>
            <el-input v-model="formInline.user" placeholder="邮箱账号或手机号码" clearable />
          </el-form-item>
          <el-form-item>
            <el-input v-model="formInline.region" show-password placeholder="输入密码" clearable />
          </el-form-item>
          <el-form-item>
            <el-checkbox v-model="formInline.date" label="30天内免登录" size="large" />
          </el-form-item>
        </el-form>
        <el-button class="large_btn" @click="handleLogin">登录</el-button>
        <p class="text_center" style="margin: 2vh 0 4vh;">
          <span>忘记密码</span> ｜
          <span>注册新账号</span>
        </p>
        <div class="footer">
          <span>其他登录方式</span>
          <span>
            <img style="width: 5vh;" src="https://github.githubassets.com/assets/GitHub-Mark-ea2971cee799.png" alt="" />
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router'
import { ref, onMounted, reactive } from 'vue'

const router = useRouter()
const formInline = reactive({
  user: '',
  region: '',
  date: '',
})

// 响应式状态
const count = ref(0)


// 生命周期钩子
onMounted(() => {
  console.log(`The initial count is ${count.value}.`)
})
const handleLogin = () => {
  router.push({
    name: 'about',
    query: {
      test: 123
    },
  })
}
</script>



<style scoped>
.wrapper {
  width: 100vw;
  height: 100vh;
  background: url('../assets/login_bg.png');
  background-size: cover;
  display: flex;
  align-items: center;
}
.container {
  width: 40vw;
  background: #fff;
  opacity: .9;
  border-radius: 2vh;
  margin: 1vh auto 0;
  padding: 2vh;
}
.loginBox {
  padding: 2vw;
}
.footer {
  display: flex;
  justify-content: space-between;
  img {
    vertical-align: middle;
  }
}
</style>
