<template>
    <div>
        <div class="mb-4">
            <el-button >Default</el-button>
            <el-button type="primary">Primary</el-button>
            <el-button size="small">Default</el-button>
            <el-button type="primary" size="small">Primary</el-button>
        </div>
        <p>
          <div><el-button type="primary" >你好</el-button></div>
           <p> <el-button type="success" >你</el-button></p>
           <p> <el-button type="success" >你好世界，时间过得真快</el-button></p>
        </p>
    </div>
</template>

<script lang="ts" setup>
import {
    Check,
    Delete,
    Edit,
    Message,
    Search,
    Star,
} from '@element-plus/icons-vue'
</script>
<style>
.mb-4 {
    padding-bottom: 10px;
}
</style>