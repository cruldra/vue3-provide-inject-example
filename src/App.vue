<template>
  <c-form ref="formRef">
    <c-form-item>
      <c-input />
    </c-form-item>
    <c-form-item>
      <c-input />
    </c-form-item>
    <c-form-item>
      <c-input />
    </c-form-item>
  </c-form>

  <button @click="submit">提交</button>
</template>
<script lang="ts" setup>
import Cform from './c-form.vue';
import CFormItem from './c-form-item.vue';
import CInput from './c-input.vue';
import {ref} from "vue";
import CForm from "@/c-form.vue";
const formRef=ref(null)
const submit=()=>{
  // alert(formRef?.value)
  formRef?.value?.validateAllInputs()
}
</script>
