
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WifiProtectedSetupRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M16.7,5.3l1.44-1.44c0.32-0.32,0.09-0.85-0.35-0.85H11.5c-0.28,0-0.5,0.22-0.5,0.5V9.8c0,0.45,0.54,0.67,0.85,0.35 l1.45-1.45c1.97,1.46,3.25,3.78,3.25,6.42c0,0.66-0.08,1.31-0.24,1.92c-0.12,0.5,0.48,0.86,0.84,0.49 c1.48-1.53,2.4-3.61,2.4-5.91C19.55,9.11,18.44,6.86,16.7,5.3z"/></g><g><path d="M12.15,13.86L10.7,15.3c-1.97-1.46-3.25-3.78-3.25-6.42c0-0.66,0.08-1.31,0.24-1.92c0.12-0.5-0.48-0.86-0.84-0.49 c-1.48,1.53-2.4,3.61-2.4,5.91c0,2.52,1.1,4.77,2.84,6.33l-1.44,1.44c-0.32,0.32-0.09,0.85,0.35,0.85h6.29 c0.28,0,0.5-0.22,0.5-0.5v-6.29C13,13.77,12.46,13.54,12.15,13.86z"/></g></g></g>
  </svg>
</template>
        