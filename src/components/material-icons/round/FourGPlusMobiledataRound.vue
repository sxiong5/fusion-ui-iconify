
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FourGPlusMobiledataRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M16,9c0.55,0,1-0.45,1-1s-0.45-1-1-1h-5C9.9,7,9,7.9,9,9v6c0,1.1,0.9,2,2,2h4c1.1,0,2-0.9,2-2v-3c0-0.55-0.45-1-1-1h-2 c-0.55,0-1,0.45-1,1s0.45,1,1,1h1v2h-4V9H16z"/><path d="M23,11h-1v-1c0-0.55-0.45-1-1-1s-1,0.45-1,1v1h-1c-0.55,0-1,0.45-1,1s0.45,1,1,1h1v1c0,0.55,0.45,1,1,1s1-0.45,1-1v-1h1 c0.55,0,1-0.45,1-1S23.55,11,23,11z"/><path d="M7,12V8c0-0.55-0.45-1-1-1S5,7.45,5,8v4H3V8c0-0.55-0.45-1-1-1S1,7.45,1,8v5c0,0.55,0.45,1,1,1h3v2c0,0.55,0.45,1,1,1 s1-0.45,1-1v-2c0.55,0,1-0.45,1-1S7.55,12,7,12z"/></g></g>
  </svg>
</template>
        