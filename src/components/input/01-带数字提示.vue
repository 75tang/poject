<template>
  <a-textarea v-model:value="value" show-count :maxlength="100" />
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const value = ref('test value');
    return {
      value,
    };
  },

});
</script>