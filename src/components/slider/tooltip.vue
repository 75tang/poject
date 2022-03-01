<template>
  <div style="display:inline-block;height:300px;">
    <h4>included=true</h4>
    <!-- tooltip-visible为true时小标签始终显示 -->
    <a-slider v-model:value='value' :marks="marks" tooltip-visible="true" vertical>
      <template #mark="{label,point}">
        <template v-if="point===100">
          <strong>{{label}}</strong>
        </template>
        <template v-else>{{label}}</template>
      </template>
    </a-slider>
  </div>
</template>

<script>
import { defineComponent,ref } from "vue"
export default defineComponent( {
  setup(){
    const value=ref(32)
    const marks=ref({
      0: '0°C',
      26: '26°C',
      37: '37°C',
      100:{
        style:{
          color:'#f50'
        },
        label:'100°C'
      }
    })
    return {
      value,
      marks
    }
  }
})
</script>

<style>

</style>