
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WifiChannelSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M16,3c-2.51,0-3.77,5.61-4.4,10.57C10.79,10.66,9.61,8,8,8C4.43,8,3,21,3,21h2.01c0.61-5.27,2-9.82,2.99-10.87 c0.98,1.05,2.38,5.61,2.99,10.87H13c0.5-2.53,2-6,3-6s2.5,3.53,3,6h2C21,21,20.5,3,16,3z M16,13c-0.99,0-1.82,0.62-2.5,1.5 c0.57-4.77,1.54-8.62,2.5-9.44c0.97,0.81,1.91,4.67,2.49,9.43C17.81,13.62,16.98,13,16,13z"/></g>
  </svg>
</template>
        