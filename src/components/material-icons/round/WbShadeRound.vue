
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WbShadeRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M14,14.13L14,14.13c0,0.23,0.09,0.46,0.26,0.63l4.98,4.98c0.17,0.17,0.39,0.26,0.62,0.26h0c0.79,0,1.18-0.95,0.62-1.51 l-4.98-4.98C14.95,12.95,14,13.35,14,14.13z M15,20h2l-3-3v2C14,19.55,14.45,20,15,20z M7.65,4.35L2.85,9.15 C2.54,9.46,2.76,10,3.21,10H4v9c0,0.55,0.45,1,1,1h6c0.55,0,1-0.45,1-1v-9h0.79c0.45,0,0.67-0.54,0.35-0.85L8.35,4.35 C8.16,4.16,7.84,4.16,7.65,4.35z M9,14H7v-4h2V14z"/></g></g>
  </svg>
</template>
        