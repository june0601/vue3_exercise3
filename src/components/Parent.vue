<template>
    <InputField v-model="name" />
    <br />
    Parent: {{name}}
    
</template>

<script>
import { ref } from "vue";
import InputField from '@/components/InputField'
export default {
  setup() {
    const name = ref("");
    return { name };
  },
  components: {
    InputField,
  }
};
</script>