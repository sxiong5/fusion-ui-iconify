
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FireExtinguisherRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M7,19h10v1c0,1.1-0.9,2-2,2H9c-1.1,0-2-0.9-2-2V19z M7,18h10v-5H7V18z M17,4.23v3.54c0,0.63-0.58,1.11-1.21,0.98 l-1.94-0.41c0,0.02,0,0.01-0.01,0.03c1.54,0.62,2.71,1.98,3.06,3.63H7.1c0.34-1.66,1.52-3.02,3.07-3.64 c-0.33-0.26-0.6-0.58-0.8-0.95L5.49,6.6C5.2,6.54,5,6.29,5,6v0c0-0.29,0.2-0.54,0.49-0.6l3.88-0.81C9.87,3.65,10.86,3,12,3 c0.7,0,1.34,0.25,1.85,0.66l1.94-0.41C16.42,3.12,17,3.6,17,4.23z M13,6c-0.03-0.59-0.45-1-1-1s-1,0.45-1,1s0.45,1,1,1 S13,6.55,13,6z"/></g>
  </svg>
</template>
        