<template>
  <h4>标签页</h4>
    <el-tabs type="border-card" class="demo-tabs">
      <el-tab-pane>
        <template #label>
          <span class="custom-tabs-label">
            <el-icon><calendar /></el-icon>
            <span>路由</span>
          </span>
        </template>
        Route
      </el-tab-pane>
      <el-tab-pane label="Config">配置</el-tab-pane>
      <el-tab-pane label="Role">角色</el-tab-pane>
      <el-tab-pane label="Task">任务</el-tab-pane>
    </el-tabs>
  </template>
  
  <script lang="ts" setup>
  import { Calendar } from '@element-plus/icons-vue'
  </script>
  
  <style>
  .demo-tabs > .el-tabs__content {
    padding: 32px;
    color: #6b778c;
    font-size: 32px;
    font-weight: 600;
  }
  .demo-tabs .custom-tabs-label .el-icon {
    vertical-align: middle;
  }
  .demo-tabs .custom-tabs-label span {
    vertical-align: middle;
    margin-left: 4px;
  }
  </style>
  