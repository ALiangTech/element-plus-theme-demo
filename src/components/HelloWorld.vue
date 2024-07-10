<script setup>
import { ref } from 'vue'
import 'dayjs/locale/en'
import { ElConfigProvider } from 'element-plus'
import zhCn from 'element-plus/es/locale/lang/zh-cn'
import en from 'element-plus/es/locale/lang/en'
import { Search } from '@element-plus/icons-vue'
import Table from './table.vue'
import Menu from './menu.vue'
import Buttons from './Button.vue'
import Dialogs from './Dialog.vue'
import Tabs from './Tabs.vue'
import { ElInput, ElDatePicker, ElButton, ElSwitch } from 'element-plus'

import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)
defineProps({
  msg: String,
})

const value1 = ref()
const textarea2 = ref()
const input1 = ref()
const value4 = ref()
const value12 = ref()
const locale = ref(zhCn)
const handleLangulang = (type = 'zhCn') => {
  locale.value = type === 'zhCn' ? zhCn : en;
}
const value = ref('')

const options = [
  {
    value: 'Option1',
    label: 'Option1',
  },
  {
    value: 'Option2',
    label: 'Option2',
  },
  {
    value: 'Option3',
    label: 'Option3',
  },
  {
    value: 'Option4',
    label: 'Option4',
  },
  {
    value: 'Option5',
    label: 'Option5',
  },
]
const popperOptions = {
  modifiers: [{ name: 'offset', options: { offset: [0, 6] } }]
}
</script>

<template>
  <section style="width: 60vw;margin: 30px auto;">
    <el-config-provider :locale="locale">
      <div style="margin-bottom: 12px;">
        <ElButton  type="primary" @click="handleLangulang('en')">切换英文</ElButton>
        <ElButton  type="primary" @click="handleLangulang('zhCn')">切换中文</ElButton>
        <ElButton  type="primary" @click="toggleDark()">黑白主题</ElButton>
        <span class="ml-2">{{ isDark ? 'Dark' : 'Light' }}</span>
      </div>
      <div style="padding-bottom: 10px;">
          <Buttons></Buttons>
        </div>
        <div style="padding-bottom: 10px;">
          <Dialogs></Dialogs>
        </div>
      <div style="width: 200px;padding-bottom: 10px;">
        <div style="padding-bottom: 10px;">
          <el-input v-model="input1" style="width: 240px" :prefix-icon="Search" />
        </div>
        <div style="padding-bottom: 10px;">
          <ElInput></ElInput>
        </div>
        <div style="padding-bottom: 10px;">
          <ElDatePicker v-model="value1" type="date" />
        </div>
        <div style="padding-bottom: 10px;">
          <el-select v-model="value" placeholder="Select" style="width: 240px" :popper-options="popperOptions">
            <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" />
          </el-select>
        </div>
        <div style="padding-bottom: 10px;">
          <el-slider v-model="value12" />
        </div>
        <div style="padding-bottom: 10px;">
          <el-select v-model="value4" multiple collapse-tags collapse-tags-tooltip :max-collapse-tags="3" :popper-options="popperOptions"
            placeholder="Select" style="width: 240px">
            <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" />
          </el-select>
        </div>
        <div style="padding-bottom: 10px;">
          <el-input v-model="textarea2" style="width: 240px" :autosize="{ minRows: 2, maxRows: 4 }" type="textarea" />
        </div>
      </div>
      <div style="padding-bottom: 10px;">
        <Tabs></Tabs>
      </div>
      <div style="padding-bottom: 10px;">
          <Table></Table>
        </div>
        <div style="--el-menu-bg-color: transparent;">
          <Menu></Menu>
        </div>
    </el-config-provider>
  </section>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
