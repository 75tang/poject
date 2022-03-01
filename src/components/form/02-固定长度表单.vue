<template>
<!-- 用col设置固定宽度 -->
  <a-form
    :model="state"
    :label-col="labelCol"
    :wrapper-col="wrapperCol"
  >
    <a-form-item
      label='Activity name'
      name='activity name'
    >
      <a-input v-model:value='state.name'></a-input>
    </a-form-item>
    <a-form-item label='delivery'>
      <a-switch v-model:value='state.delivery'/>
    </a-form-item>
    <a-form-item
    label='type'
    name='type'
    >
      <a-checkbox-group v-model:value='state.type'>
        <a-checkbox value="1">111</a-checkbox>
        <a-checkbox value='2'>222</a-checkbox>
        <a-checkbox value='3'>333</a-checkbox>
      </a-checkbox-group>
    </a-form-item>
    <a-form-item label='resources'>
      <a-radio-group v-model:value='state.radio'>
        <a-radio value="4">444</a-radio>
        <a-radio value="5">555</a-radio>
      </a-radio-group>
    </a-form-item>
    <a-form-item label='form'>
      <a-input v-model:value='state.form' type="textarea"></a-input>
    </a-form-item>
    <a-form-item :wrapper-col="{span:14,offset:4}">
      <a-button type='primary' @click="onSubmit">Create</a-button>
      <a-button style="margin-left:10px">Cancel</a-button>
    </a-form-item>
  </a-form>
</template>

<script>
import { defineComponent,reactive,toRaw,  } from "vue";

export default defineComponent({
  setup(){
    const state = reactive({
      name:'',
      delivery:false,
      type:[],
      radio:'',
      form:''
    })
    const onSubmit =() => {
      console.log('submit!',toRaw(state))
    }
    return {
      labelCol:{
        style:{
          width:'150px'
        }
      },
      wrapperCol:{
          span:10
      },
      state,
      onSubmit,
    }
  }

})
</script>

<style>

</style>