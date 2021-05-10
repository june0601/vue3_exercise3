<template>
  <section>
    <input placeholder="num1" type="number" v-model.number="num1" />
    <select v-model="operand">
      <option value="+"> + </option>
      <option value="-"> - </option>
      <option value="*"> * </option>
      <option value="/"> / </option>
    </select>
    <input placeholder="num2" type="number" v-model.number="num2" />
    <h2> {{ret}} </h2>
  </section>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operand: "",
    };
  },
  computed: {
    ret() {
      switch (this.operand) {
        case "+":
          return this.num1 + this.num2;
        case "-":
          return this.num1 - this.num2;
        case "*":
          return this.num1 * this.num2;
        case "/":
          return this.num1 / this.num2;
      }
    }
  }
};
</script>
