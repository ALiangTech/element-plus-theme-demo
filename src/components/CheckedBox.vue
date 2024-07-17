<template>
    <div>
        <h4>多选框</h4>
    </div>
    <div>
        <el-checkbox v-model="checked1" label="Option 1" size="large" />
        <el-checkbox v-model="checked2" label="Option 2" size="large" />
    </div>
    <div>
        <el-checkbox v-model="checked3" label="Option 1" />
        <el-checkbox v-model="checked4" label="Option 2" />
    </div>
    <div>
        <el-checkbox v-model="checked5" label="Option 1" size="small" />
        <el-checkbox v-model="checked6" label="Option 2" size="small" />
    </div>
    <div>
        <el-checkbox v-model="checked7" label="Option 1" size="small" disabled />
        <el-checkbox v-model="checked8" label="Option 2" size="small" disabled />
    </div>
    <div>中间态</div>
    <el-checkbox v-model="checkAll" :indeterminate="isIndeterminate" @change="handleCheckAllChange">
        Check all
    </el-checkbox>
    <el-checkbox-group v-model="checkedCities" @change="handleCheckedCitiesChange">
        <el-checkbox v-for="city in cities" :key="city" :label="city" :value="city">
            {{ city }}
        </el-checkbox>
    </el-checkbox-group>
    <div>按钮组模式</div>
    <div>
        <el-checkbox-group v-model="checkboxGroup1" size="large">
            <el-checkbox-button v-for="city in cities" :key="city" :value="city">
                {{ city }}
            </el-checkbox-button>
        </el-checkbox-group>
    </div>
    <div class="demo-button-style">
        <el-checkbox-group v-model="checkboxGroup2">
            <el-checkbox-button v-for="city in cities" :key="city" :value="city">
                {{ city }}
            </el-checkbox-button>
        </el-checkbox-group>
    </div>
    <div class="demo-button-style">
        <el-checkbox-group v-model="checkboxGroup3" size="small">
            <el-checkbox-button v-for="city in cities" :key="city" :value="city" :disabled="city === 'Beijing'">
                {{ city }}
            </el-checkbox-button>
        </el-checkbox-group>
    </div>
    <div class="demo-button-style">
        <el-checkbox-group v-model="checkboxGroup4" size="small" disabled>
            <el-checkbox-button v-for="city in cities" :key="city" :value="city">
                {{ city }}
            </el-checkbox-button>
        </el-checkbox-group>
    </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const checked1 = ref(true)
const checked2 = ref(false)
const checked3 = ref(false)
const checked4 = ref(false)
const checked5 = ref(false)
const checked6 = ref(false)
const checked7 = ref(false)
const checked8 = ref(false)

const checkboxGroup1 = ref(['Shanghai'])
const checkboxGroup2 = ref(['Shanghai'])
const checkboxGroup3 = ref(['Shanghai'])
const checkboxGroup4 = ref(['Shanghai'])
const checkAll = ref(false)
const isIndeterminate = ref(true)
const checkedCities = ref(['Shanghai', 'Beijing'])
const cities = ['Shanghai', 'Beijing', 'Guangzhou', 'Shenzhen']

const handleCheckAllChange = (val: boolean) => {
    checkedCities.value = val ? cities : []
    isIndeterminate.value = false
}
const handleCheckedCitiesChange = (value: string[]) => {
    const checkedCount = value.length
    checkAll.value = checkedCount === cities.length
    isIndeterminate.value = checkedCount > 0 && checkedCount < cities.length
}
</script>

<style scoped>
.demo-button-style {
  margin-top: 24px;
}
</style>