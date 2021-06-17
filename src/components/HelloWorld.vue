<template>
  <h3>{{text}}</h3>
  <input />
</template>

<script lang="ts">
import useCurrencyInput, { CurrencyInputOptions } from "vue-currency-input";
import { computed, defineComponent } from "vue";

export default defineComponent({
  name: "HelloWorld",
  props: {
    condition: { type: Object}
  },
  setup(props) {
    const options: CurrencyInputOptions = {
      currency: "EUR"
    }

    const { formattedValue, inputRef } = useCurrencyInput(options)

    const text = computed(() => {
      if (props.condition?.isOk) {
        return "Lalala";
      }
      return "Bababab";
    });


    return { text, inputRef, formattedValue }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
