<template>
  <div class="login-container">
    <div class="login-box">
      <h2 class="login-title">Login</h2>
      <t-input
        v-model="password"
        type="password"
        placeholder="密码"
        :show-password="true"
        class="password-input"
      />
      <t-button class="login-button" @click="handleLogin">登录</t-button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
import { TInput, TButton } from 'tdesign-vue-next'

export default {
  components: {
    TInput,
    TButton,
  },
  setup() {
    const password = ref('')

    const handleLogin = () => {
      if (!password.value) {
        alert("请输入密码")
        return
      }
      // 在此处添加登录逻辑
      console.log("登录成功")
    }

    return {
      password,
      handleLogin,
    }
  },
}
</script>

<style scoped>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #7f7fd5, #86a8e7, #91eae4);
}

.login-box {
  width: 300px;
  padding: 30px;
  border-radius: 10px;
  background: #ffffff;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.login-title {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 20px;
  color: #333;
}

.password-input {
  width: 100%;
  margin-bottom: 20px;
}

.login-button {
  width: 100%;
}
</style>
