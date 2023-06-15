<script setup lang="ts">
const emit = defineEmits(['login'])

const onLogin = () => {
  emit('login')
}
</script>

<template>
  <h2 class="text-2xl text-center mb-6">欢迎注册</h2>
  <form>
    <div class="mb-3">
      <input
        type="email"
        id="email"
        class="bg-white border border-gray-300 text-gray-900 text-sm rounded focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
        placeholder="支持电子邮箱注册"
        required
      />
    </div>
    <div class="mb-6">
      <input
        type="password"
        id="password"
        class="bg-white border border-gray-300 text-gray-900 text-sm rounded focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
        required
        placeholder="请输入密码"
      />
    </div>
    <div class="mb-6">
      <button
        type="submit"
        class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded text-sm w-full px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
      >
        创建账户
      </button>
    </div>

    <div class="flex flex-col items-center text-sm space-y-4">
      <div class="text-xs text-center">
        点击“创建帐户”，即表示您同意 <span class="text-blue-500"> TRY-VUE3 服务协议</span> 和
        <span class="text-blue-500">隐私政策</span>
      </div>
      <div>已有账户？<span class="text-blue-500" @click="onLogin">登录</span></div>
    </div>
  </form>
</template>
