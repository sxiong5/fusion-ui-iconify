
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WifiTetheringErrorRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M10.66,7.14c-2.24,0.48-4.04,2.3-4.52,4.54c-0.37,1.75,0.02,3.38,0.89,4.66c0.34,0.51,1.08,0.55,1.51,0.11l0,0 c0.35-0.35,0.37-0.88,0.1-1.28c-0.5-0.76-0.75-1.71-0.61-2.73c0.23-1.74,1.67-3.17,3.41-3.4C13.9,8.71,16,10.61,16,13 c0,0.8-0.24,1.54-0.64,2.16c-0.27,0.41-0.25,0.95,0.1,1.29l0,0c0.43,0.43,1.17,0.4,1.51-0.11C17.62,15.4,18,14.25,18,13 C18,9.25,14.55,6.3,10.66,7.14z M10.25,3.15c-4.05,0.69-7.19,3.69-8.03,7.72c-0.66,3.17,0.2,6.16,1.97,8.38 c0.37,0.46,1.07,0.49,1.49,0.07l0,0c0.36-0.36,0.39-0.93,0.07-1.32c-1.34-1.67-2.03-3.9-1.66-6.28c0.55-3.47,3.42-6.24,6.92-6.65 c2.76-0.33,5.27,0.74,6.93,2.59C18.14,7.87,18.41,8,18.7,8h0c0.85,0,1.34-1.01,0.77-1.65C17.28,3.9,13.91,2.53,10.25,3.15z M12,11 c-1.1,0-2,0.9-2,2c0,0.55,0.23,1.05,0.59,1.41C10.95,14.77,11.45,15,12,15s1.05-0.23,1.41-0.59C13.77,14.05,14,13.55,14,13 C14,11.9,13.1,11,12,11z M21,10L21,10c0.55,0,1,0.45,1,1v4c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1v-4C20,10.45,20.45,10,21,10z M21,18L21,18c0.55,0,1,0.45,1,1v0c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1v0C20,18.45,20.45,18,21,18z"/></g></g>
  </svg>
</template>
        