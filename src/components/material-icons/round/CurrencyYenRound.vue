
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CurrencyYenRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M6.82,3c0.34,0,0.66,0.17,0.84,0.46L12,10.29l4.34-6.83C16.52,3.17,16.84,3,17.18,3c0.79,0,1.27,0.87,0.84,1.54L13.92,11 H17c0.55,0,1,0.45,1,1c0,0.55-0.45,1-1,1h-4v2h4c0.55,0,1,0.45,1,1c0,0.55-0.45,1-1,1h-4v3c0,0.55-0.45,1-1,1s-1-0.45-1-1v-3H7 c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1h4v-2H7c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1h3.08L5.98,4.54C5.55,3.87,6.03,3,6.82,3z"/></g>
  </svg>
</template>
        