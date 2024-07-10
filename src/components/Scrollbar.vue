<template>
    <h4>滚动条</h4>
    <p>纵向</p>
    <el-scrollbar height="400px">
      <p v-for="item in 20" :key="item" class="scrollbar-demo-item">{{ item }}</p>
    </el-scrollbar>
    <p>横向</p>
    <el-scrollbar>
    <div class="scrollbar-flex-content">
      <p v-for="item in 50" :key="item" class="scrollbar-demo-itemy">
        {{ item }}
      </p>
    </div>
  </el-scrollbar>
  </template>
  
  <style scoped>
  .scrollbar-demo-item {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
    margin: 10px;
    text-align: center;
    border-radius: 4px;
    background: var(--el-color-primary-light-9);
    color: var(--el-color-primary);
  }
  </style>
  <style scoped>
  .scrollbar-flex-content {
    display: flex;
  }
  .scrollbar-demo-itemy {
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100px;
    height: 50px;
    margin: 10px;
    text-align: center;
    border-radius: 4px;
    background: var(--el-color-danger-light-9);
    color: var(--el-color-danger);
  }
  </style>