<template>
  <input type="text" v-model="internalValue" v-on:blur="onBlur" />
</template>

<script lang="ts" setup>
import { ref, inject, onMounted, onUnmounted } from 'vue';

const internalValue = ref('');
const legal = ref(true);

const onBlur = () => {
  legal.value =
    internalValue.value !== undefined &&
    internalValue.value !== null &&
    internalValue.value !== '';

  alert("校验结果:"+legal.value)
};

const registerInput = inject('registerInput');
const unregisterInput = inject('unregisterInput');
const validate=onBlur
onMounted(() => {
  registerInput && registerInput({ validate });
});

onUnmounted(() => {
  unregisterInput && unregisterInput({ validate });
});
</script>
