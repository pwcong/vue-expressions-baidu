![preview](https://github.com/pwcong/SnapShot/blob/master/react-expressions/demo.gif?raw=true)

# vue-expressions-baidu
A Vue Component about Baidu Expressions.

## Install
```
npm install --save vue-expressions-baidu
```

## Usage

```html

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
```


```js
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

```

## API

* BaiduExpressionsPicker [ vue component ]

    props:

    * pickerClass [ string ]
    * symbolClass [ string ]
    * onSymbolClick [ func ]

* BaiduExpressionsSymbol [ vue component ]

    props:

    * symbol [ string | required]
    * className [ string ]

* isSymbol [ func | str[string] -> bool ]

    check if `str` is a valid symbol.

* SYMBOLS [ object ]

    get symbol dataURL using key