
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TungstenRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M12,19L12,19c-0.56,0-1,0.45-1,1V21c0,0.55,0.45,1,1,1H12c0.55,0,1-0.45,1-1V20C13,19.45,12.55,19,12,19z"/><path d="M5.99,17.09L5.28,17.8c-0.39,0.39-0.39,1.02,0,1.41c0.39,0.39,1.02,0.39,1.41,0l0.71-0.71c0.39-0.39,0.39-1.02,0-1.41 C7.02,16.71,6.38,16.71,5.99,17.09z"/><path d="M5,12c0-0.55-0.45-1-1-1H3c-0.55,0-1,0.45-1,1V12c0,0.55,0.45,1,1,1H4C4.55,13,5,12.55,5,12L5,12z"/><path d="M21,11H20c-0.55,0-1,0.45-1,1V12c0,0.55,0.45,1,1,1H21c0.55,0,1-0.45,1-1V12C22,11.45,21.55,11,21,11z"/><path d="M18.01,17.09c-0.39-0.39-1.02-0.39-1.41,0c-0.39,0.39-0.39,1.02,0,1.41l0.71,0.71c0.39,0.39,1.02,0.39,1.41,0 c0.39-0.39,0.39-1.02,0-1.41L18.01,17.09z"/><path d="M15,8.02V5c0-1.1-0.9-2-2-2h-2C9.9,3,9,3.9,9,5v3.02c-1.43,1.08-2.28,2.9-1.91,4.91c0.36,1.95,1.9,3.55,3.84,3.95 C14.16,17.56,17,15.11,17,12C17,10.37,16.21,8.94,15,8.02z M13,7.1C12.68,7.04,12.34,7,12,7s-0.68,0.04-1,0.1V5h2V7.1z"/></g></g>
  </svg>
</template>
        