<style lang="scss">
.baidu-expressions-symbol {
  display: inline-block;
  width: 30px;
  height: 30px;
  background-size: 100%;
  background-repeat: no-repeat;
}
</style>

<template>
    <span 
        :class="{
            'baidu-expressions-symbol': true,
            [className]: className ? true : false
        }"
        :style="{
            backgroundImage: 'url(' + symbol + ')'
        }">
    </span>
</template>
<script>
export default {
  props: {
    symbol: {
      type: String,
      required: true
    },
    className: {
      type: String
    }
  }
};
</script>
