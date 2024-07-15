<template>
    <div>
        <div class="mb-4">
            <el-button style="--el-button-hover-text-color:#4e5969;--el-button-hover-bg-color:#e5e6eb">Default</el-button>
            <el-button type="primary">Primary</el-button>
            <el-button type="success">Success</el-button>
            <el-button type="info">Info</el-button>
            <el-button type="warning">Warning</el-button>
            <el-button type="danger">Danger</el-button>
        </div>

        <div class="mb-4">
            <el-button plain style="--el-button-hover-text-color:#4e5969;--el-button-hover-bg-color:#e5e6eb">Plain</el-button>
            <el-button type="primary" plain>Primary</el-button>
            <el-button type="success" plain>Success</el-button>
            <el-button type="info" plain>Info</el-button>
            <el-button type="warning" plain>Warning</el-button>
            <el-button type="danger" plain>Danger</el-button>
        </div>

        <div class="mb-4">
            <el-button round style="--el-button-hover-text-color:#4e5969;--el-button-hover-bg-color:#e5e6eb">Round</el-button>
            <el-button type="primary" round>Primary</el-button>
            <el-button type="success" round>Success</el-button>
            <el-button type="info" round>Info</el-button>
            <el-button type="warning" round>Warning</el-button>
            <el-button type="danger" round>Danger</el-button>
        </div>

        <div>
            <el-button :icon="Search" circle style="--el-button-hover-text-color:#4e5969;--el-button-hover-bg-color:#e5e6eb"/>
            <el-button type="primary" :icon="Edit" circle />
            <el-button type="success" :icon="Check" circle />
            <el-button type="info" :icon="Message" circle />
            <el-button type="warning" :icon="Star" circle />
            <el-button type="danger" :icon="Delete" circle />
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