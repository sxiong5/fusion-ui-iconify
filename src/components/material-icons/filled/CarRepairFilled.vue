
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CarRepairFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M16.22,12c0.68,0,1.22-0.54,1.22-1.22c0-0.67-0.54-1.22-1.22-1.22S15,10.11,15,10.78C15,11.46,15.55,12,16.22,12z M6.56,10.78c0,0.67,0.54,1.22,1.22,1.22S9,11.46,9,10.78c0-0.67-0.54-1.22-1.22-1.22S6.56,10.11,6.56,10.78z M7.61,4L6.28,8h11.43 l-1.33-4H7.61z M16.28,3c0,0,0.54,0.01,0.92,0.54c0.02,0.02,0.03,0.04,0.05,0.07c0.07,0.11,0.14,0.24,0.19,0.4 C17.66,4.66,19,8.69,19,8.69v6.5c0,0.45-0.35,0.81-0.78,0.81h-0.44C17.35,16,17,15.64,17,15.19V14H7v1.19C7,15.64,6.65,16,6.22,16 H5.78C5.35,16,5,15.64,5,15.19v-6.5c0,0,1.34-4.02,1.55-4.69c0.05-0.16,0.12-0.28,0.19-0.4C6.77,3.58,6.78,3.56,6.8,3.54 C7.18,3.01,7.72,3,7.72,3H16.28z M4,17.01h16V19h-7v3h-2v-3H4V17.01z"/></g>
  </svg>
</template>
        