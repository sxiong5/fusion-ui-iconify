
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TransferWithinAStationRound',
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
     xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"
  >
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M22 15.5h-5.52v-.77c0-.36-.44-.54-.69-.29l-1.51 1.52c-.16.16-.16.41 0 .57l1.51 1.52c.26.26.69.08.69-.29V17H22v-1.5zm-.28 4.71l-1.51-1.52c-.26-.26-.69-.08-.69.29v.77H14v1.5h5.52v.77c0 .36.44.54.69.29l1.51-1.52c.16-.16.16-.42 0-.58zM9.5 5.5c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2zM5.75 8.9L3.23 21.81c-.12.62.35 1.19.98 1.19h.09c.47 0 .88-.33.98-.79L6.85 15 9 17v5c0 .55.45 1 1 1s1-.45 1-1v-5.72c0-.53-.21-1.04-.59-1.41L8.95 13.4l.6-3c1.07 1.32 2.58 2.23 4.31 2.51.6.1 1.14-.39 1.14-1 0-.49-.36-.9-.84-.98-1.49-.25-2.75-1.15-3.51-2.38l-.95-1.6C9.35 6.35 8.7 6 8 6c-.25 0-.5.05-.75.15L3.24 7.79C2.49 8.1 2 8.83 2 9.64V12c0 .55.45 1 1 1s1-.45 1-1V9.65l1.75-.75"/>
  </svg>
</template>
        