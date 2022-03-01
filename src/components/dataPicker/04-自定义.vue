<template>
  <a-space direction="vertical" :size="12">
    <a-date-picker v-model:value="value1" :format="dateFormat" />
    <a-date-picker v-model:value="value2" :format="dateFormatList" />
    <a-date-picker v-model:value="value3" :format="monthFormat" picker="month" />
    <a-range-picker v-model:value="value4" :format="dateFormat" />
    <a-date-picker v-model:value="value5" :format="customFormat" />
  </a-space>
</template>
<script src="https://unpkg.com/dayjs">
import dayjs from 'dayjs';
dayjs().format;
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const dateFormat = 'YYYY/MM/DD';
    const monthFormat = 'YYYY/MM';
    const dateFormatList = ['DD/MM/YYYY', 'DD/MM/YY'];
    return {
      value1: ref(dayjs('2015/01/01', dateFormat)),
      value2: ref(dayjs('01/01/2015', dateFormatList[0])),
      value3: ref(dayjs('2015/01', monthFormat)),
      value4: ref([dayjs('2015/01/01', dateFormat), dayjs('2015/01/01', dateFormat)]),
      value5: ref(dayjs('2015/01/01', dateFormat)),
      dateFormat,
      monthFormat,
      dateFormatList,
      customFormat: value => `custom format: ${value.format(dateFormat)}`,
    };
  },

});
</script>