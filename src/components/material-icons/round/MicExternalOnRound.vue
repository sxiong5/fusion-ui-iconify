
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MicExternalOnRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M9.22,7H4.78C4.3,6.47,4,5.77,4,5c0-1.66,1.34-3,3-3s3,1.34,3,3C10,5.77,9.7,6.47,9.22,7z M16.24,2.01 C18.32,2.13,20,4.08,20,6.16L20,21c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1l0-14.91c0-0.96-0.64-1.86-1.58-2.05 C15.14,3.78,14,4.76,14,6l0,11.84c0,2.08-1.68,4.03-3.76,4.15C7.92,22.13,6,20.29,6,18H5.45c-0.26,0-0.47-0.19-0.5-0.45L4.11,9.1 C4.05,8.51,4.51,8,5.1,8H8.9c0.59,0,1.05,0.51,1,1.1l-0.85,8.45C9.02,17.81,8.8,18,8.55,18H8c0,1.24,1.14,2.22,2.42,1.96 c0.94-0.19,1.58-1.09,1.58-2.05L12,6C12,3.71,13.92,1.87,16.24,2.01z"/></g></g>
  </svg>
</template>
        