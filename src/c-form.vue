<script setup lang="ts">
import { ref, provide } from 'vue';

const inputInstances = ref([]);

const registerInput = (instance) => {
  inputInstances.value.push(instance);
};

const unregisterInput = (instance) => {
  inputInstances.value = inputInstances.value.filter((i) => i !== instance);
};

provide('registerInput', registerInput);
provide('unregisterInput', unregisterInput);


const validateAllInputs = () => {
  inputInstances.value.forEach((instance) => {
    instance.validate();
  });
};

defineExpose({validateAllInputs})
</script>

<template>
  <slot></slot>
</template>
