
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SignalWifiStatusbarConnectedNoInternet3Twotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M17,9V8h5.92C19.97,5.51,16.16,4,12,4C7.31,4,3.07,5.9,0,8.98l2.82,2.82C5.17,9.45,8.41,8,12,8 C13.77,8,15.46,8.36,17,9z" fill-opacity=".3"/><g><path d="M2.82,11.8L12,21l5-5.01V9c-1.54-0.64-3.23-1-5-1C8.41,8,5.17,9.45,2.82,11.8z"/><rect height="2" width="2" x="19" y="18"/><rect height="6" width="2" x="19" y="10"/></g></g>
  </svg>
</template>
        