
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MacroOffFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M19.98,17.15C20.63,15.91,21,14.5,21,13c-1.5,0-2.91,0.37-4.15,1.02L19.98,17.15z"/><path d="M3,13c0,4.97,4.03,9,9,9C12,17.03,7.97,13,3,13z"/><path d="M12,5.5c1.38,0,2.5,1.12,2.5,2.5c0,0.99-0.58,1.84-1.42,2.25l2.48,2.48c0.11,0.02,0.23,0.03,0.35,0.03 c1.38,0,2.5-1.12,2.5-2.5c0-1-0.59-1.85-1.43-2.25c0.84-0.4,1.43-1.25,1.43-2.25c0-1.38-1.12-2.5-2.5-2.5 c-0.53,0-1.01,0.16-1.42,0.44L14.5,3.5C14.5,2.12,13.38,1,12,1S9.5,2.12,9.5,3.5l0.02,0.19C9.12,3.41,8.63,3.25,8.1,3.25 c-0.57,0-1.09,0.2-1.51,0.52l3.16,3.16C10.16,6.08,11.01,5.5,12,5.5z"/><path d="M2.81,2.81L1.39,4.22l4.64,4.64C5.76,9.26,5.6,9.73,5.6,10.25c0,1.38,1.12,2.5,2.5,2.5c0.52,0,0.99-0.16,1.4-0.43 l0.02,0.02L9.5,12.5c0,1.38,1.12,2.5,2.5,2.5c0.05,0,0.1-0.01,0.16-0.02l1.64,1.64C12.67,18.12,12,19.98,12,22 c2.02,0,3.88-0.67,5.38-1.8l2.4,2.4l1.41-1.41L2.81,2.81z"/></g></g>
  </svg>
</template>
        