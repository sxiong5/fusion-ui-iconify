
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NotificationAddRound',
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
    <rect fill="none" height="24" width="24" x="0" y="0"/><g><path d="M10,20h4c0,1.1-0.9,2-2,2S10,21.1,10,20z M14,9c0,2.61,1.67,4.83,4,5.66L18,17h1c0.55,0,1,0.45,1,1v0c0,0.55-0.45,1-1,1H5 c-0.55,0-1-0.45-1-1v0c0-0.55,0.45-1,1-1h1v-7c0-2.79,1.91-5.14,4.5-5.8V3.5C10.5,2.67,11.17,2,12,2s1.5,0.67,1.5,1.5v0.7 c0.71,0.18,1.36,0.49,1.95,0.9C14.54,6.14,14,7.51,14,9z M23,8h-2V6c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v2h-2 c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h2v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-2h2c0.55,0,1-0.45,1-1v0 C24,8.45,23.55,8,23,8z"/></g>
  </svg>
</template>
        