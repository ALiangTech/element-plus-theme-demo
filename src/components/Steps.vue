<template>
    <h4>步骤</h4>
    <el-steps style="max-width: 600px" :active="active" finish-status="success">
        <el-step title="Step 1" />
        <el-step title="Step 2" />
        <el-step title="Step 3" />
    </el-steps>

    <el-button style="margin-top: 12px" @click="next">Next step</el-button>
    <p style="height: 300px; max-width: 600px">
        <el-steps direction="vertical" :active="1">
            <el-step title="Step 1" />
            <el-step title="Step 2" />
            <el-step title="Step 3" />
        </el-steps>
    </p>
    <p>
    <p>
        <el-steps class="mb-4" style="max-width: 600px" :space="200" :active="1" simple>
            <el-step title="Step 1" :icon="Edit" />
            <el-step title="Step 2" :icon="UploadFilled" />
            <el-step title="Step 3" :icon="Picture" />
        </el-steps>
    </p>

    <el-steps style="max-width: 600px" :active="1" finish-status="success" simple>
        <el-step title="Step 1" />
        <el-step title="Step 2" />
        <el-step title="Step 3" />
    </el-steps>
    </p>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { Edit, Picture, UploadFilled } from '@element-plus/icons-vue'
const active = ref(0)

const next = () => {
    if (active.value++ > 2) active.value = 0
}
</script>