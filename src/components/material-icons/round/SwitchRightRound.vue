
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SwitchRightRound',
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
    <rect fill="none" height="24" transform="matrix(-1 -1.224647e-16 1.224647e-16 -1 24 24)" width="24"/><path d="M15.5,15.38V8.62L18.88,12L15.5,15.38 M20.29,12.71c0.39-0.39,0.39-1.02,0-1.41l-4.59-4.59C15.08,6.08,14,6.52,14,7.41v9.17 c0,0.89,1.08,1.34,1.71,0.71L20.29,12.71z M10,16.59V7.41c0-0.89-1.08-1.34-1.71-0.71l-4.59,4.59c-0.39,0.39-0.39,1.02,0,1.41 l4.59,4.59C8.92,17.92,10,17.48,10,16.59z"/>
  </svg>
</template>
        