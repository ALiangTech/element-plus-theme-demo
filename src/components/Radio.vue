<template>
    <h4>单选</h4>
    <div class="mb-2 flex items-center text-sm">
      <el-radio-group v-model="radio1" class="ml-4">
        <el-radio value="1" size="large">Option 1</el-radio>
        <el-radio value="2" size="large">Option 2</el-radio>
      </el-radio-group>
    </div>
    <div style="margin-top: 20px">
    <el-radio-group v-model="radio4">
      <el-radio-button label="New York" value="New York" />
      <el-radio-button label="Washington" value="Washington" />
      <el-radio-button label="Los Angeles" value="Los Angeles" />
      <el-radio-button label="Chicago" value="Chicago" />
    </el-radio-group>
  </div>
  </template>
  
  <script lang="ts" setup>
  import { ref } from 'vue'
  
  const radio1 = ref('1')
  const radio2 = ref('1')
  const radio3 = ref('1')
  const radio4 = ref('Washington')
  </script>
  