<template>
  <a-tree-select
    v-model:value="value"
    style="width: 100%"
    placeholder="Please select"
    :tree-data="treeData"
  >
    <template #title="{ value: val, title }">
      <b v-if="val === 'parent 1-1'" style="color: #08c">sss</b>
      <template v-else>{{ title }}</template>
    </template>
  </a-tree-select>
</template>
<script>
import { defineComponent, ref, watch } from 'vue';
export default defineComponent({
  setup() {
    const value = ref();
    const treeData = ref([{
      title: 'parent 1',
      value: 'parent 1',
      children: [{
        title: 'parent 1-0',
        value: 'parent 1-0',
        children: [{
          title: 'my leaf',
          value: 'leaf1',
        }, {
          title: 'your leaf',
          value: 'leaf2',
        }],
      }, {
        title: 'parent 1-1',
        value: 'parent 1-1',
      }],
    }]);
    watch(value, () => {
      console.log(value.value);
    });
    return {
      value,
      treeData,
    };
  },

});
</script>