
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SwipeDownSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M3.8,12.18c-0.2-0.86-0.3-1.76-0.3-2.68c0-2.84,0.99-5.45,2.63-7.5L7.2,3.07C5.82,4.85,5,7.08,5,9.5 c0,0.88,0.11,1.74,0.32,2.56l1.62-1.62L8,11.5L4.5,15L1,11.5l1.06-1.06L3.8,12.18z"/><path d="M21.71,11.18l2.09,7.39l-8.23,3.65l-6.84-2.85l0.61-1.62l3.8-0.75L8.79,7.17c-0.34-0.76,0-1.64,0.76-1.98 c0.76-0.34,1.64,0,1.98,0.76l2.43,5.49l1.26-0.56L21.71,11.18z"/></g>
  </svg>
</template>
        