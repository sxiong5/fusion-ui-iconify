
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SignalWifiConnectedNoInternet3Twotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M21.18,11.8L24,8.98C20.93,5.9,16.69,4,12,4C7.31,4,3.07,5.9,0,8.98l2.82,2.82C5.17,9.45,8.41,8,12,8 S18.83,9.45,21.18,11.8z" fill-opacity=".3"/><path d="M21.18,11.8C18.83,9.45,15.59,8,12,8s-6.83,1.45-9.18,3.8L12,21v-9h8.99L21.18,11.8z M19.59,14l-2.09,2.09L15.41,14 L14,15.41l2.09,2.09L14,19.59L15.41,21l2.09-2.08L19.59,21L21,19.59l-2.08-2.09L21,15.41L19.59,14z"/></g></g>
  </svg>
</template>
        