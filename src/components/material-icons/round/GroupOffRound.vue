
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'GroupOffRound',
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
    <rect fill="none" height="24" width="24"/><path d="M15,8c0-1.42-0.5-2.73-1.33-3.76C14.09,4.1,14.53,4,15,4c2.21,0,4,1.79,4,4s-1.79,4-4,4c-0.06,0-0.12,0-0.18,0l-0.77-0.77 C14.65,10.29,15,9.18,15,8z M7.24,4.41C7.77,4.15,8.37,4,9,4c2.21,0,4,1.79,4,4c0,0.63-0.15,1.23-0.41,1.76L7.24,4.41z M21.19,21.19 c0.39,0.39,0.39,1.02,0,1.41s-1.02,0.39-1.41,0l-2.99-2.99C16.6,19.85,16.32,20,16,20H2c-0.55,0-1-0.45-1-1v-2c0-2.66,5.33-4,8-4 c0.37,0,0.8,0.03,1.25,0.08L9.17,12C9.11,12,9.06,12,9,12c-2.21,0-4-1.79-4-4c0-0.06,0-0.11,0-0.17L1.39,4.22 C1,3.83,1,3.2,1.39,2.81s1.02-0.39,1.41,0L21.19,21.19z M18.89,16.07c-0.29-1.22-1.13-2.19-2.23-2.94C19.42,13.53,23,14.82,23,17v2 c0,0.32-0.15,0.6-0.38,0.79L18.89,16.07z"/>
  </svg>
</template>
        