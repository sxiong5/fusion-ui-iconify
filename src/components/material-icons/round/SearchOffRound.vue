
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SearchOffRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M15.5,14h-0.79l-0.28-0.27c1.2-1.4,1.82-3.31,1.48-5.34c-0.47-2.78-2.79-4.99-5.58-5.34C6.54,2.58,3.3,5.38,3.03,9h2.02 c0.24-2.12,1.92-3.8,4.06-3.98C11.65,4.8,14,6.95,14,9.5c0,2.49-2.01,4.5-4.5,4.5c-0.17,0-0.33-0.03-0.5-0.05l0,2.02 c0,0,0,0,0.01,0.01c1.8,0.13,3.47-0.47,4.72-1.55L14,14.71v0.79l4.25,4.25c0.41,0.41,1.08,0.41,1.49,0l0,0 c0.41-0.41,0.41-1.08,0-1.49L15.5,14z"/><path d="M6.12,11.17L4,13.29l-2.12-2.12c-0.2-0.2-0.51-0.2-0.71,0l0,0c-0.2,0.2-0.2,0.51,0,0.71L3.29,14l-2.12,2.12 c-0.2,0.2-0.2,0.51,0,0.71l0,0c0.2,0.2,0.51,0.2,0.71,0L4,14.71l2.12,2.12c0.2,0.2,0.51,0.2,0.71,0l0,0c0.2-0.2,0.2-0.51,0-0.71 L4.71,14l2.12-2.12c0.2-0.2,0.2-0.51,0-0.71l0,0C6.63,10.98,6.32,10.98,6.12,11.17z"/></g></g>
  </svg>
</template>
        