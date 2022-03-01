<template>
  <div>
      <a-row>
          <a-col :span="12"><a-slider v-model:value='value1' :min="1" :max="25"></a-slider></a-col>
          <a-col :span="4"><a-input-number v-model:value='value1' :min="10" :max="25"/></a-col>
      </a-row>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
    setup(){
        const value1 = ref()
        return {
            value1
        }
    }
})
</script>

<style>

</style>