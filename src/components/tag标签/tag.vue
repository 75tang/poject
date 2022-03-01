<template>
  <div>
      <a-tag>tag 1</a-tag>
      <a-tag><a href="#">link</a></a-tag>
      <a-tag closable @close='log'>tag 2</a-tag>
      <a-tag closable @close.prevent>tag 3</a-tag>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
    setup(){
        const log = e =>{
            console.log(e)
        }
        return{
            log
        }
    }

})
</script>

<style>

</style>