
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'QueryStatsRound',
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
    <rect fill="none" height="24" width="24"/><g><path d="M19.88,18.47c0.48-0.77,0.75-1.67,0.69-2.66c-0.13-2.15-1.84-3.97-3.97-4.2c-2.72-0.3-5.02,1.81-5.02,4.47 c0,2.49,2.01,4.5,4.49,4.5c0.88,0,1.7-0.26,2.39-0.7l2.41,2.41c0.39,0.39,1.03,0.39,1.42,0v0c0.39-0.39,0.39-1.03,0-1.42 L19.88,18.47z M16.08,18.58c-1.38,0-2.5-1.12-2.5-2.5c0-1.38,1.12-2.5,2.5-2.5s2.5,1.12,2.5,2.5 C18.58,17.46,17.46,18.58,16.08,18.58z M15.72,10.08c-0.74,0.02-1.45,0.18-2.1,0.45l-0.55-0.83l-3.08,5.01 c-0.36,0.58-1.17,0.64-1.61,0.13l-2.12-2.47l-3.06,4.9c-0.31,0.49-0.97,0.62-1.44,0.28l0,0c-0.42-0.31-0.54-0.89-0.26-1.34 l3.78-6.05c0.36-0.57,1.17-0.63,1.61-0.12L9,12.5l3.18-5.17c0.38-0.62,1.28-0.64,1.68-0.03L15.72,10.08z M18.31,10.58 c-0.64-0.28-1.33-0.45-2.05-0.49L20.8,2.9c0.31-0.49,0.97-0.61,1.43-0.27l0,0c0.43,0.31,0.54,0.9,0.26,1.34L18.31,10.58z"/></g>
  </svg>
</template>
        