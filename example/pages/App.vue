<template>
    <div class="container">
      
      <baidu-expressions-picker
        pickerClass="picker"
        symbolClass="symbol"
        :onSymbolClick="handleSymbolClick"/>

      <div class="symbols">

        <baidu-expressions-symbol 
          v-for="(symbol, idx) in symbols"
          :key="'symbols-item-' + idx"
          :symbol="symbol"/>

      </div>

    </div>
</template>

<style lang="scss">
.container {
  .picker {
    box-sizing: border-box;
    padding: 4px;
    max-width: 328px;
    margin: 0 auto;
    box-shadow: 0 0 5px #ccc;
    border-radius: 4px;
  }

  .symbol {
    margin: 1px;
    cursor: pointer;

    &:hover {
      outline: 2px solid #41b883;
    }
  }

  .symbols {
    box-sizing: border-box;
    padding: 16px;
  }
}
</style>

<script>
import {
  BaiduExpressionsPicker,
  BaiduExpressionsSymbol,
  isSymbol,
  SYMBOLS
} from "../../src/index";

export default {
  data() {
    return {
      symbols: []
    };
  },
  components: {
    BaiduExpressionsPicker,
    BaiduExpressionsSymbol
  },
  methods: {
    handleSymbolClick(symbol) {
      if (isSymbol(symbol)) {
        this.symbols.push(SYMBOLS[symbol]);
      }
    }
  }
};
</script>
