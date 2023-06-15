<script setup lang="ts">
import { ref } from 'vue'

import LoginForm from './components/LoginForm.vue'
import CreateAccountForm from './components/CreateAccountForm.vue'

const switchFormFlag = ref(true)
const switchForm = () => {
  switchFormFlag.value = !switchFormFlag.value
}
</script>

<template>
  <div class="w-full h-screen flex flex-col justify-between">
    <div class="flex justify-center items-center p-2 space-x-2.5 text-xs text-slate-500">
      <div class="flex items-center">
        <!-- 待改进内容，打算写一个Bootstrap弹窗 -->
        <label for="displayMode"> 显示模式：</label>
        <select
          id="displayMode"
          class="bg-gray-50 border border-gray-300 rounded focus:ring-blue-500 focus:border-blue-500 px-2 p-1 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
        >
          <option>浅色</option>
          <option>暗色</option>
        </select>
      </div>

      <div>版本号：1.2.3</div>
    </div>

    <div class="flex-1 flex flex-col justify-center items-center my-8">
      <div class="text-center space-y-5 mb-10">
        <div class="flex justify-center items-center">
          <img src="@/assets/logo.svg" alt="logo" srcset="" class="w-11 h-11" />
          <span class="text-5xl ml-2">TRY-VUE3</span>
        </div>
        <div class="text-sm text-slate-500">
          这是一个使用 Vue3 完成前端项目的编码、测试、部署的项目。
        </div>
      </div>

      <div class="w-full px-6 flex justify-center">
        <div class="w-full flex p-10 rounded bg-gray-100 md:space-x-10 max-w-4xl">
          <img
            src="@/assets/login-firmware.svg"
            alt="firmware"
            srcset=""
            class="hidden md:block w-1/2"
          />

          <div class="flex-1">
            <LoginForm v-if="switchFormFlag" @createAccount="switchForm"/>
            <CreateAccountForm v-else @login="switchForm"/>
          </div>
        </div>
      </div>
    </div>

    <div class="text-center text-xs text-slate-500 p-2">Copyright © 2023 Tianlin-W</div>
  </div>
</template>
