
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WebhookRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M2,16c0-1.84,1-3.45,2.48-4.32C5.15,11.29,6,11.76,6,12.54c0,0.36-0.19,0.68-0.5,0.86C4.6,13.92,4,14.89,4,16 c0,1.85,1.68,3.31,3.6,2.94c1.42-0.28,2.4-1.61,2.4-3.06v0c0-0.49,0.39-0.88,0.88-0.88l5,0c0.27-0.31,0.67-0.5,1.12-0.5 c0.83,0,1.5,0.67,1.5,1.5c0,0.83-0.67,1.5-1.5,1.5c-0.44,0-0.84-0.19-1.12-0.5l-3.98,0c-0.46,2.28-2.48,4-4.9,4 C4.24,21,2,18.76,2,16z M16.37,7c0.65,0,1.14-0.62,0.97-1.25C16.79,3.59,14.83,2,12.5,2c-2.76,0-5,2.24-5,5 c0,1.43,0.6,2.71,1.55,3.62l-2.35,3.9C6.02,14.66,5.5,15.27,5.5,16c0,0.83,0.67,1.5,1.5,1.5s1.5-0.67,1.5-1.5 c0-0.16-0.02-0.31-0.07-0.45l2.86-4.75c0.25-0.41,0.13-0.95-0.28-1.19C10.11,9.08,9.5,8.11,9.5,7c0-1.65,1.35-3,3-3 c1.38,0,2.54,0.93,2.89,2.2C15.52,6.66,15.9,7,16.37,7z M17,13c-0.38,0-0.75,0.07-1.09,0.2c-0.4,0.16-0.86-0.04-1.08-0.41 l-2.6-4.32C11.53,8.35,11,7.74,11,7c0-0.83,0.67-1.5,1.5-1.5S14,6.17,14,7c0,0.15-0.02,0.29-0.06,0.43l2.19,3.65 C16.41,11.03,16.7,11,17,11l0,0c2.76,0,5,2.24,5,5c0,2.76-2.24,5-5,5c-0.86,0-1.68-0.22-2.39-0.61c-0.92-0.5-0.58-1.89,0.47-1.89 c0.17,0,0.34,0.05,0.49,0.14C15.99,18.87,16.48,19,17,19c1.65,0,3-1.35,3-3S18.65,13,17,13z"/></g>
  </svg>
</template>
        