
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ScreenLockRotationRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M20.41,11.36l-0.35-0.35c-0.39-0.39-1.02-0.39-1.41,0c-0.39,0.39-0.39,1.02,0,1.41L19,12.77l-4.24,4.24L6.98,9.23 l4.24-4.24l0.35,0.35c0.39,0.39,1.02,0.39,1.41,0c0.39-0.39,0.39-1.02,0-1.41l-0.35-0.36c-0.79-0.79-2.03-0.79-2.82,0L5.57,7.82 c-0.78,0.78-0.78,2.05,0,2.83l7.78,7.78c0.79,0.79,2.03,0.79,2.82,0l4.24-4.24C21.2,13.41,21.2,12.14,20.41,11.36z"/><path d="M10.85,17.85C10.54,17.54,10,17.76,10,18.21v1.53c-3.17-0.82-5.59-3.54-5.95-6.86C3.99,12.37,3.56,12,3.06,12 c-0.6,0-1.07,0.53-1,1.12C2.62,18.11,6.87,22,12,22c0.59,0,1.17-0.06,1.73-0.16c0.4-0.07,0.55-0.56,0.27-0.85L10.85,17.85z"/><path d="M16,9h4c0.55,0,1-0.45,1-1V5c0-0.55-0.45-1-1-1V3.11c0-1-0.68-1.92-1.66-2.08C17.08,0.82,16,1.79,16,3v1 c-0.55,0-1,0.45-1,1v3C15,8.55,15.45,9,16,9z M17,3c0-0.55,0.45-1,1-1s1,0.45,1,1v1h-2V3z"/></g></g>
  </svg>
</template>
        