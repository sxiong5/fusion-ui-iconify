
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'JoinInnerOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><ellipse cx="12" cy="12" rx="3" ry="5.74"/><g><path d="M9.04,16.87C8.71,16.95,8.36,17,8,17c-2.76,0-5-2.24-5-5s2.24-5,5-5c0.36,0,0.71,0.05,1.04,0.13 c0.39-0.56,0.88-1.12,1.49-1.63C9.75,5.19,8.9,5,8,5c-3.86,0-7,3.14-7,7s3.14,7,7,7c0.9,0,1.75-0.19,2.53-0.5 C9.92,17.99,9.43,17.43,9.04,16.87z"/></g><path d="M16,5c-0.9,0-1.75,0.19-2.53,0.5c0.61,0.51,1.1,1.07,1.49,1.63C15.29,7.05,15.64,7,16,7c2.76,0,5,2.24,5,5s-2.24,5-5,5 c-0.36,0-0.71-0.05-1.04-0.13c-0.39,0.56-0.88,1.12-1.49,1.63C14.25,18.81,15.1,19,16,19c3.86,0,7-3.14,7-7S19.86,5,16,5z"/></g>
  </svg>
</template>
        