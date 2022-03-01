<template>
  <a-alert message="Success Text" type="success" />
  <a-alert message="Info Text" type="info" />
  <a-alert message="Warning Text" type="warning" closable @close="onClose"/>
  <a-alert message="Error Text" type="error" />
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
    setup(){
        const onClose = e =>{
            console.log(e,'closed.')
        }
        return{
            onClose
        }
    }
})
</script>

<style>

</style>