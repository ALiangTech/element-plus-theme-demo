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
import Link from './Link.vue'
import Radio from './Radio.vue'
import Switch from './Switch.vue'
import Dates from './Date.vue'
import Uploads from './Upload.vue'
import Drawers from './Drawer.vue'
import Popconfirm from './Popconfirm.vue'
import Breadcrumb from './Breadcrumb.vue'
import Pagination from './Pagination.vue'
import Steps from './Steps.vue'
import Scrollbar from './Scrollbar.vue'
import CheckedBox from './CheckedBox.vue'
import { ElInput, ElDatePicker, ElButton } from 'element-plus'
import Finger from './finger.vue'
import Select from './Select.vue'
import SearchLogo from './../assets/search.svg'

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
        <ElButton type="primary" @click="handleLangulang('en')">切换英文</ElButton>
        <ElButton type="primary" @click="handleLangulang('zhCn')">切换中文</ElButton>
        <ElButton type="primary" @click="toggleDark()">黑白主题</ElButton>
        <span class="ml-2">{{ isDark ? 'Dark' : 'Light' }}</span>
      </div>
      <div style="padding-bottom: 10px;">
        <h4>按钮</h4>
        <Buttons></Buttons>
      </div>
      <div>
        <h4>链接</h4>
        <Link />
      </div>
      <div>
          <h4>输入框</h4>
          <div style="padding-bottom: 10px;">
            <el-input v-model="input1" style="width: 240px">
              <template #prefix>
                  <img :src="SearchLogo" style="width: 16px; height: 16px;">
              </template>
            </el-input>
          </div>
          <div style="padding-bottom: 10px;">
            <ElInput style="width: 240px"></ElInput>
          </div>
          <div>
            <el-input v-model="textarea2" style="width: 240px" :autosize="{ minRows: 2, maxRows: 4 }" type="textarea" />
          </div>
      </div>
      <div>
        <h4>标签输入框</h4>
        <p>无</p>
      </div>
      <Select></Select>
      <Radio></Radio>
      <CheckedBox></CheckedBox>
      <Switch></Switch>
      <Dates></Dates>
      <Uploads></Uploads>
      <Drawers></Drawers>
      <Dialogs></Dialogs>
      <Popconfirm></Popconfirm>
      <Breadcrumb></Breadcrumb>
      <Pagination></Pagination>
      <Steps></Steps>
      <Scrollbar></Scrollbar>
      <Table></Table>
      <Menu></Menu>
      <Tabs></Tabs>
      <Finger></Finger>
    </el-config-provider>
  </section>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
