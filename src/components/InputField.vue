<template>
      Child: {{ input }}
      <input 
      type="text" 
      placeholder="Name" 
      v-model="name" 
      @input="$emit('update:modelValue', $event.target.value)"
      />
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const input = ref("");
    return { input };
  },
};
</script>