
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SwipeRightSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M20.18,15.4L19.1,23h-9L5,17.62l1.22-1.23L10,17.24V6.5C10,5.67,10.67,5,11.5,5S13,5.67,13,6.5v6h1.38L20.18,15.4z M19.91,5.5H17V7h5V2h-1.5v2.02C18.18,2.13,15.22,1,12,1C6.51,1,2.73,4.12,2,7h1.57C4.33,5.02,7.26,2.5,12,2.5 C15.03,2.5,17.79,3.64,19.91,5.5z"/></g>
  </svg>
</template>
        