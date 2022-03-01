<template>
  <a-space direction="vertical" :size="12">
    <a-range-picker v-model:value="value1" />
    <a-range-picker v-model:value="value2" show-time />
    <a-range-picker v-model:value="value3" picker="week" />
    <a-range-picker v-model:value="value4" picker="month" />
    <a-range-picker v-model:value="value5" picker="year" />
  </a-space>
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    return {
      value1: ref(),
      value2: ref(),
      value3: ref(),
      value4: ref(),
      value5: ref(),
    };
  },

});
</script>