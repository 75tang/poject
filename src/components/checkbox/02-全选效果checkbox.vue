<template>
  <div>
    <a-checkbox
      v-model:checked="checkAll"
      :indeterminate="indeterminate"
    ><!-- indeterminate全选效果 -->
      Check all
    </a-checkbox>
  </div>
  <a-divider /><!-- 分割线 -->
  <a-checkbox-group v-model:value="checkedList" :options="plainOptions" />
</template>
<script>
import { defineComponent, reactive, toRefs, watch } from 'vue';
const plainOptions = ['Apple', 'Pear', 'Orange'];
export default defineComponent({
  setup() {
    const state = reactive({
      indeterminate: true,
      checkAll: false,
      checkedList: ['Apple', 'Orange'],
    });

    const onCheckAllChange = e => {
      Object.assign(state, {
        checkedList: e.target.checked ? plainOptions : [],
        indeterminate: false,
      });
    };

    watch(() => state.checkedList, val => {
      state.indeterminate = !!val.length && val.length < plainOptions.length;
      state.checkAll = val.length === plainOptions.length;
    });
    return { ...toRefs(state),
      plainOptions,
      onCheckAllChange,
    };
  },

});
</script>