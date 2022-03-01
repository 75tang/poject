<template>
  <a-button type="primary" @click="info">display</a-button>
  <a-button @click="success">11111</a-button>
  <a-button @click="error">2222</a-button>
  <a-button @click="warning">33333</a-button>
</template>

<script>
/*自定义时常10秒，默认时常3秒 */
import { defineComponent } from "vue";
import {message} from "ant-design-vue"
export default defineComponent({
  setup(){
    const info = () =>{
      message.info('this is a normal message',10)
    }
    const success =()=>{
      message.loading('111111',2.5).then(()=>message.success('22222',2.5),
      ()=>{}).then(()=>info('33333',2.5));
    }
    const error =()=>{
      message.error('error')
    }
    const warning =()=>{
      message.warning('warning')
    }
    return{
      info,
      success,
      error,
      warning,
    }
  }
})
</script>

<style>

</style>