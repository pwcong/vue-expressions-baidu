<style lang="scss">
.baidu-expressions-picker {
  width: 100%;
}
</style>

<template>
  
    <div :class="{
        'baidu-expressions-picker': true,
        [pickerClass]: pickerClass ? true : false
        }"
        @click="handlePickerClick">

        <baidu-expressions-symbol 
            v-for="(symbol, key) in symbols" 
            :key="'baidu-expressions-symbol-' + key"
            :className="symbolClass"
            :symbol="symbol"
            :data-symbol="key"/>

    </div>

</template>

<script>
import BaiduExpressionsSymbol from "./Symbol.vue";

import SYMBOLS from "./symbols";

export default {
  props: {
    pickerClass: {
      type: String
    },
    symbolClass: {
      type: String
    },
    onSymbolClick: {
      type: Function,
      default: symbol => {
        console.log(symbol);
      }
    }
  },
  data() {
    return {
      symbols: SYMBOLS
    };
  },
  methods: {
    handlePickerClick(e) {
      const symbol = e.target.getAttribute("data-symbol");

      if (symbol) {
        this.onSymbolClick(symbol);
      }
    }
  },
  components: {
    BaiduExpressionsSymbol
  }
};
</script>


