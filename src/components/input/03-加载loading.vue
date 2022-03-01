<template>
  <div>
    <a-input-search v-model:value="value" placeholder="input search loading deault" loading />
    <br />
    <br />
    <a-input-search
      v-model:value="value"
      placeholder="input search loading with enterButton"
      loading
      enter-button='search'
    />
  </div>
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