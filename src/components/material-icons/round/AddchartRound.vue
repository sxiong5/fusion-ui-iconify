
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AddchartRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M16,17c0.55,0,1-0.45,1-1v-2c0-0.55-0.45-1-1-1s-1,0.45-1,1v2C15,16.55,15.45,17,16,17z"/><path d="M20,10c-0.55,0-1,0.45-1,1v8H5V5h8c0.55,0,1-0.45,1-1s-0.45-1-1-1H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14 c1.1,0,2-0.9,2-2v-8C21,10.45,20.55,10,20,10z"/><path d="M7,11v5c0,0.55,0.45,1,1,1s1-0.45,1-1v-5c0-0.55-0.45-1-1-1S7,10.45,7,11z"/><path d="M11,8v8c0,0.55,0.45,1,1,1s1-0.45,1-1V8c0-0.55-0.45-1-1-1S11,7.45,11,8z"/><path d="M16,7h1v1c0,0.55,0.45,1,1,1s1-0.45,1-1V7h1c0.55,0,1-0.45,1-1s-0.45-1-1-1h-1V4c0-0.55-0.45-1-1-1s-1,0.45-1,1v1h-1 c-0.55,0-1,0.45-1,1S15.45,7,16,7z"/></g></g>
  </svg>
</template>
        