
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SmartScreenRound',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><g><path d="M21,5H3C1.9,5,1,5.9,1,7v10c0,1.1,0.9,2,2,2h18c1.1,0,2-0.9,2-2V7C23,5.9,22.1,5,21,5z M18,7v10H6V7H18z M14,12 c0-0.41-0.34-0.75-0.75-0.75S12.5,11.59,12.5,12s0.34,0.75,0.75,0.75S14,12.41,14,12z M9,12c0-0.41-0.34-0.75-0.75-0.75 S7.5,11.59,7.5,12s0.34,0.75,0.75,0.75S9,12.41,9,12z M16.5,12c0-0.41-0.34-0.75-0.75-0.75S15,11.59,15,12s0.34,0.75,0.75,0.75 S16.5,12.41,16.5,12z M11.5,12c0-0.41-0.34-0.75-0.75-0.75S10,11.59,10,12s0.34,0.75,0.75,0.75S11.5,12.41,11.5,12z"/></g></g>
  </svg>
</template>
        