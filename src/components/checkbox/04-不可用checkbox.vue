<template>
  <a-checkbox v-model:checked="checked1" disabled />
  <br />
  <a-checkbox v-model:checked="checked2" disabled />
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    return {
      checked1: ref(false),
      checked2: ref(true),
    };
  },

});
</script>