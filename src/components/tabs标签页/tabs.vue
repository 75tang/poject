<template>
  <a-tabs v-model:activeKey="activeKey" centered>
      <a-tab-pane key="1">
        <template #tab>
          <span>
            <apple-outlined/>
            pane1
          </span>
        </template>
        pane 1
      </a-tab-pane>
      <a-tab-pane key="2">
        <template #tab>
          <span>
            <android-outlined/>
            pane2
          </span>
        </template>
        pane 2
      </a-tab-pane>
      <a-tab-pane key="3" tab="Tab 3">pane3</a-tab-pane>
  </a-tabs>
</template>

<script>
import { defineComponent,ref } from "vue";
import {AppleOutlined,AndroidOutlined} from '@ant-design/icons-vue'
export default defineComponent({
  components:{
    AppleOutlined,
    AndroidOutlined
  },
    setup(){
        return{
            activeKey:ref('1')
        }
    }
})
</script>

<style>

</style>