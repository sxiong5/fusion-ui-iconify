
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CarCrashRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M18,1c-2.76,0-5,2.24-5,5s2.24,5,5,5s5-2.24,5-5S20.76,1,18,1z M18,7c-0.28,0-0.5-0.22-0.5-0.5v-3C17.5,3.22,17.72,3,18,3 s0.5,0.22,0.5,0.5v3C18.5,6.78,18.28,7,18,7z M18.5,8.5C18.5,8.78,18.28,9,18,9s-0.5-0.22-0.5-0.5S17.72,8,18,8 S18.5,8.22,18.5,8.5z M19.5,20c0.82,0,1.5-0.67,1.5-1.5v-6.18c-1.05,0.51-2.16,0.69-3.09,0.68c0.06,0.16,0.09,0.33,0.09,0.5 c0,0.83-0.67,1.5-1.5,1.5S15,14.33,15,13.5c0-0.39,0.15-0.74,0.39-1.01c-1.63-0.66-2.96-1.91-3.71-3.49H5.81l1.04-3H11 c0-0.69,0.1-1.37,0.29-2H6.5C5.84,4,5.29,4.42,5.08,5.01l-1.97,5.67C3.04,10.89,3,11.11,3,11.34v7.16C3,19.33,3.67,20,4.5,20 S6,19.33,6,18.5V18h12v0.5C18,19.33,18.68,20,19.5,20z M7.5,15C6.67,15,6,14.33,6,13.5S6.67,12,7.5,12S9,12.67,9,13.5 S8.33,15,7.5,15z"/></g></g>
  </svg>
</template>
        