
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SignalWifiConnectedNoInternet1Twotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M12,12h8.99L24,8.98C20.93,5.9,16.69,4,12,4C7.31,4,3.07,5.9,0,8.98l6.35,6.36 C7.79,13.89,9.79,13,12,13V12z" fill-opacity=".3"/><path d="M12,21v-8c-2.21,0-4.2,0.89-5.65,2.34L12,21z M21,15.41L19.59,14l-2.09,2.09L15.41,14L14,15.41l2.09,2.09L14,19.59 L15.41,21l2.09-2.08L19.59,21L21,19.59l-2.08-2.09L21,15.41z"/></g></g>
  </svg>
</template>
        