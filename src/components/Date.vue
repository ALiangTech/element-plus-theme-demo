<template>
    <div>
        <h4>日期/时间选择器</h4>
        <div>
            <div class="demonstration">默认</div>
            <el-date-picker v-model="value1" type="daterange" range-separator="To" start-placeholder="Start date"
            popper-class="y-arrow-hidden"
            :prefix-icon="customPrefix"
                :popper-options="{
                    modifiers: [
                        {
                            name: 'offset',
                            options: {
                                offset: [0, 4],
                            },
                        },
                    ],
                }" end-placeholder="End date" :size="size" />
        </div>
        <div>
            <div>With quick options</div>
            <el-date-picker v-model="value2" type="daterange" unlink-panels range-separator="To" popper-class="y-arrow-hidden" :popper-options="{
                modifiers: [
                    {
                        name: 'offset',
                        options: {
                            offset: [0, 4],
                        },
                    },
                ],
            }" start-placeholder="Start date" end-placeholder="End date" :shortcuts="shortcuts" :size="size"   :prefix-icon="customPrefix"/>
        </div>
        <div>
            <div class="demonstration">日期时间</div>
            <el-date-picker v-model="value3" type="datetime" placeholder="Select date and time" popper-class="y-arrow-hidden" :prefix-icon="customPrefixForTime" :popper-options="{
                modifiers: [
                    {
                        name: 'offset',
                        options: {
                            offset: [0, 4],
                        },
                    },
                ],
            }" />
        </div>
        <div>
            <div>时间选择器</div>
            <el-time-picker v-model="value4" placeholder="Arbitrary time" :prefix-icon="customPrefixForTime" popper-class="y-arrow-hidden" :popper-options="{
                modifiers: [
                    {
                        name: 'offset',
                        options: {
                            offset: [0, 4],
                        },
                    },
                ],
            }" />
        </div>
    </div>
</template>

<script lang="ts" setup>
import { h } from 'vue';
import { ref } from 'vue'
import calander from './../assets/calendar.svg';
import Time from './../assets/time.svg'

const size = ref<'default' | 'large' | 'small'>('default')

const value1 = ref('')
const value2 = ref('')
const value3 = ref('')
const value4 = ref('')
const value5 = ref('')

const shortcuts = [
    {
        text: 'Last week',
        value: () => {
            const end = new Date()
            const start = new Date()
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 7)
            return [start, end]
        },
    },
    {
        text: 'Last month',
        value: () => {
            const end = new Date()
            const start = new Date()
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 30)
            return [start, end]
        },
    },
    {
        text: 'Last 3 months',
        value: () => {
            const end = new Date()
            const start = new Date()
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 90)
            return [start, end]
        },
    },
]

const prefix = (icon) => h('img', {
    src: icon,
    style: {
        height: '16px',
        width: '16px'
    }
})

const customPrefix = () => prefix(calander)
const customPrefixForTime = () => prefix(Time)
</script>