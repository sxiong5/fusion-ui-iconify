
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SwipeDownFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M3.8,12.18c-0.2-0.86-0.3-1.76-0.3-2.68c0-2.84,0.99-5.45,2.63-7.5L7.2,3.07C5.82,4.85,5,7.08,5,9.5 c0,0.88,0.11,1.74,0.32,2.56l1.62-1.62L8,11.5L4.5,15L1,11.5l1.06-1.06L3.8,12.18z M13.85,11.62l-2.68-5.37 c-0.37-0.74-1.27-1.04-2.01-0.67C8.41,5.96,8.11,6.86,8.48,7.6l4.81,9.6L10.05,18c-0.33,0.09-0.59,0.33-0.7,0.66L9,19.78l6.19,2.25 c0.5,0.17,1.28,0.02,1.75-0.22l5.51-2.75c0.89-0.45,1.32-1.48,1-2.42l-1.43-4.27c-0.27-0.82-1.04-1.37-1.9-1.37h-4.56 c-0.31,0-0.62,0.07-0.89,0.21L13.85,11.62"/></g>
  </svg>
</template>
        