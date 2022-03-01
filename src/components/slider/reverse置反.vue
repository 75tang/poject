<template>
  <div>
    <a-slider v-model:value="value1" :reverse="reverse" />
    <a-slider v-model:value="value2" range :reverse="reverse" />
    Reversed:
    <a-switch v-model:checked="reverse" size="small" />
  </div>
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const value1 = ref(30);
    const value2 = ref([20, 50]);
    const reverse = ref(true);
    return {
      value1,
      value2,
      reverse,
    };
  },

});
</script>