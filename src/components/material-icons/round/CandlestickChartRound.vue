
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CandlestickChartRound',
  props: svgIconProps,
  setup(props) {
    const fontSize = computed(() => {
      const _size = +props.size;
      if (isNaN(_size)) {
        const [_, size, unit] = /(d+)(w+)/.exec(props.size as string) || [];
        return unit === 'px' ? pxToRem(+size) : props.size;
      } else {
        return pxToRem(_size);
      }
    });

    return {
      fontSize,
      color: props.color
    };
  }
}
</script>

<template>
  <svg class="fn-icon-material fn-icon"
    :style="{ '--fn-icon-font-size': fontSize, '--fn-icon-color': $props.color }"
     xmlns="http://www.w3.org/2000/svg" enable-background="new 0 0 24 24" height="24" viewBox="0 0 24 24" width="24"
  >
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M8,4L8,4C7.45,4,7,4.45,7,5v1H6C5.45,6,5,6.45,5,7v10c0,0.55,0.45,1,1,1h1v1c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-1h1 c0.55,0,1-0.45,1-1V7c0-0.55-0.45-1-1-1H9V5C9,4.45,8.55,4,8,4z"/></g><g><path d="M18,8h-1V5c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v3h-1c-0.55,0-1,0.45-1,1v5c0,0.55,0.45,1,1,1h1v4c0,0.55,0.45,1,1,1 h0c0.55,0,1-0.45,1-1v-4h1c0.55,0,1-0.45,1-1V9C19,8.45,18.55,8,18,8z"/></g></g></g>
  </svg>
</template>
        