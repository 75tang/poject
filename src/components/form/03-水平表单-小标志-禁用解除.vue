<template>
  <a-form 
    :model="state"
    layout="inline"
    @finish="handleFinish"
    @finishFailed="handleFinishFailed"
  >
    <a-form-item>
      <a-input v-model:value='state.username' placeholder="Username">
        <template #prefix><UserOutlined style="color:rgba(0,0,0,0.25)"/></template>
      </a-input>
    </a-form-item>
    <a-form-item>
      <a-input v-model:value='state.password' placeholder="Password">
        <template #prefix><LockOutlined style="color:rgba(0,0,0,0.25)"/></template>
      </a-input>
    </a-form-item>
    <a-form-item>
      <a-button type='primary' 
      :disabled="state.username===''||state.password===''"
      >Log in</a-button><!-- 禁用达到该条件可解除 -->
    </a-form-item>
  </a-form>
</template>

<script>
import {UserOutlined,LockOutlined} from '@ant-design/icons-vue'
import { defineComponent, reactive } from "vue";
export default defineComponent({
  components:{
    UserOutlined,
    LockOutlined,
  },
  setup(){
    const state = reactive ({
      username:'',
      password:''
    })
    const handleFinish = values => {
      console.log(values,state)
    }
    const handleFinishFailed =errors =>{
      console.log(errors)
      }
    return {
      state,
      handleFinish,
      handleFinishFailed,

    }
  }
})
</script>

<style>

</style>