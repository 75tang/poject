<template>
  <div>
    <a-input v-model:value="value1" placeholder="input with clear icon" allow-clear />
    <br />
    <br />
    <a-textarea v-model:value="value2" placeholder="textarea with clear icon" allow-clear />
  </div>
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const value1 = ref('');
    const value2 = ref('');
    return {
      value1,
      value2,
    };
  },

});
</script>