<template>
  <div id="components-slider-demo-mark">
    <h4>included=true</h4>
    <!-- mark属性标注分段式滑块 -->
    <div style="display:inline-block;height:300px;">
        <a-slider v-model:value="value1" :marks="marks">
        <template #mark="{ label, point }">
            <template v-if="point === 100">
            <strong>{{ label }}</strong>
            </template>
            <template v-else>{{ label }}</template>
        </template>
        </a-slider>
    </div>
    <a-slider v-model:value="value2" range :marks="marks">
      <template #mark="{ label, point }">
        <template v-if="point === 100">
          <strong>{{ label }}</strong>
        </template>
        <template v-else>{{ label }}</template>
      </template>
    </a-slider>
    <!-- included=false 表明不同标记之间并列关系-->
    <h4>included=false</h4>
    <a-slider v-model:value="value3" :marks="marks" :included="false">
      <template #mark="{ label, point }">
        <template v-if="point === 100">
          <strong>{{ label }}</strong>
        </template>
        <template v-else>{{ label }}</template>
      </template>
    </a-slider>
    <!-- step=“10” 可选值为10的整数倍，step=null可选值仅有mark标记出来的部分 -->
    <h4>marks & step</h4>
    <a-slider v-model:value="value4" :marks="marks" :step="10">
      <template #mark="{ label, point }">
        <template v-if="point === 100">
          <strong>{{ label }}</strong>
        </template>
        <template v-else>{{ label }}</template>
      </template>
    </a-slider>

    <h4>step=null</h4>
    <a-slider v-model:value="value5" :marks="marks" :step="null">
      <template #mark="{ label, point }">
        <template v-if="point === 100">
          <strong>{{ label }}</strong>
        </template>
        <template v-else>{{ label }}</template>
      </template>
    </a-slider>
  </div>
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const value1 = ref(37);
    const value2 = ref([26, 37]);
    const value3 = ref(37);
    const value4 = ref(37);
    const value5 = ref(37);
    const marks = ref({
      0: '0°C',
      26: '26°C',
      37: '37°C',
      100: {
        style: {
          color: '#f50',
        },
        label: '100°C',
      },
    });
    return {
      value1,
      value2,
      value3,
      value4,
      value5,
      marks,
    };
  },

});
</script>
<style scoped>
#components-slider-demo-mark h4 {
  margin: 0 0 16px;
}
#components-slider-demo-mark .ant-slider-with-marks {
  margin-bottom: 44px;
}
</style>