<template>
  <div>
    <a-radio v-model:checked="checked1" :disabled="disabled">Disabled</a-radio>
    <br />
    <a-radio v-model:checked="checked2" :disabled="disabled">Disabled</a-radio>
    <div :style="{ marginTop: 20 }">
      <a-button type="primary" @click="toggleDisabled">Toggle disabled</a-button>
    </div>
  </div>
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const disabled = ref(true);
    const checked1 = ref(false);
    const checked2 = ref(false);

    const toggleDisabled = () => {
      disabled.value = !disabled.value;
    };

    return {
      disabled,
      checked1,
      checked2,
      toggleDisabled,
    };
  },

});
</script>