<template>
  <a-textarea v-model:value="value" placeholder="Basic usage" :rows="4" :bordered="false" />
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const value = ref('');
    return {
      value,
    };
  },

});
</script>