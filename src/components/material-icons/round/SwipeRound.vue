
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SwipeRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M21.15,2.85l-1.02,1.02C18.69,2.17,15.6,1,12,1S5.31,2.17,3.87,3.87L2.85,2.85C2.54,2.54,2,2.76,2,3.21V6.5 C2,6.78,2.22,7,2.5,7h3.29c0.45,0,0.67-0.54,0.35-0.85L4.93,4.93c1-1.29,3.7-2.43,7.07-2.43s6.07,1.14,7.07,2.43l-1.22,1.22 C17.54,6.46,17.76,7,18.21,7h3.29C21.78,7,22,6.78,22,6.5V3.21C22,2.76,21.46,2.54,21.15,2.85z"/><path d="M14.5,12.71c-0.28-0.14-0.58-0.21-0.89-0.21H13v-6C13,5.67,12.33,5,11.5,5S10,5.67,10,6.5v10.74l-3.44-0.72 c-0.37-0.08-0.76,0.04-1.03,0.31l0,0c-0.43,0.44-0.43,1.14,0.01,1.58l4.01,4.01C9.92,22.79,10.43,23,10.96,23h6.41 c1,0,1.84-0.73,1.98-1.72l0.63-4.46c0.12-0.85-0.32-1.69-1.09-2.07L14.5,12.71z"/></g></g>
  </svg>
</template>
        