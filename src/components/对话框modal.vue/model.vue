<template>
  <a-button type="primary" @click="model">
      open model
  </a-button>
  <a-model v-model:visible="visible" title="basic model" @ok="ok">
      <p>some1</p>
      <p>some2</p>
      <p>some3</p>
  </a-model>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
    setup(){
       const visible=ref(false)
       const model=()=>{
           visible.value=true;
       }
       const ok = e =>{
           console.log(e);
           visible.value=false;
       }
       return {
           visible,
           model,
           ok,
       }
    }

})
</script>

<style>

</style>