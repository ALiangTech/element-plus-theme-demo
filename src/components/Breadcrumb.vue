<template>
<section>
    <h4>面包屑</h4>
    <el-breadcrumb :separator-icon="ArrowRight">
        <el-breadcrumb-item>
                <a href="/">首页</a>
            </el-breadcrumb-item>
            <el-breadcrumb-item>
                <a href="/">测试</a>
            </el-breadcrumb-item>
        <el-breadcrumb-item>测试页</el-breadcrumb-item>
    </el-breadcrumb>
    <p>
        <el-breadcrumb separator="/">
            <el-breadcrumb-item>
                <a href="/">promotion management</a>
            </el-breadcrumb-item>
            <el-breadcrumb-item>promotion detail</el-breadcrumb-item>
        </el-breadcrumb>
    </p>
</section>
</template>

<script lang="ts" setup>
import { ArrowRight } from '@element-plus/icons-vue'
</script>