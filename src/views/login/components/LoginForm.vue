<script setup lang="ts">
import { useRouter } from 'vue-router'
// TODO:记住账户功能应该默认提供
const emit = defineEmits(['createAccount'])
const router = useRouter()

const onCreateAccount = () => {
  emit('createAccount')
}

const onLogin = () => {
  router.push({ name: 'Home' })
}
</script>

<template>
  <h2 class="text-2xl text-center mb-6">密码登录</h2>
  <form>
    <div class="mb-3">
      <input
        type="email"
        id="email"
        class="bg-white border border-gray-300 text-gray-900 text-sm rounded focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
        placeholder="支持电子邮箱登录"
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
        @click="onLogin"
      >
        登 录
      </button>
    </div>

    <div class="flex flex-col items-center text-sm space-y-4">
      <div href="" class="text-blue-500">重置密码</div>
      <div>没有账户？<span class="text-blue-500" @click="onCreateAccount">创建一个</span></div>
      <div class="flex items-center h-5">
        <input
          id="remember"
          type="checkbox"
          value=""
          class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-blue-300 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-blue-600 dark:ring-offset-gray-800 dark:focus:ring-offset-gray-800"
        />
        <label for="remember" class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">
          下次自动登录
        </label>
      </div>
    </div>
  </form>
</template>
