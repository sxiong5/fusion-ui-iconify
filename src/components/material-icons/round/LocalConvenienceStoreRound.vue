
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LocalConvenienceStoreRound',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><path d="M21.9,7.89l-1.05-3.37c-0.22-0.9-1-1.52-1.91-1.52H5.05c-0.9,0-1.69,0.63-1.9,1.52L2.1,7.89C1.64,9.86,2.95,11,3,11.06V19 c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2v-7.94C22.12,9.94,22.09,8.65,21.9,7.89z M13,5h1.96l0.54,3.52C15.59,9.23,15.11,10,14.22,10 C13.55,10,13,9.41,13,8.69V5z M6.44,8.86C6.36,9.51,5.84,10,5.23,10C4.3,10,3.88,9.03,4.04,8.36L5.05,5h1.97L6.44,8.86z M10.5,16H9 v1h1.5c0.28,0,0.5,0.22,0.5,0.5l0,0c0,0.28-0.22,0.5-0.5,0.5h-2C8.22,18,8,17.78,8,17.5v-2C8,15.22,8.22,15,8.5,15H10v-1H8.5 C8.22,14,8,13.78,8,13.5v0C8,13.22,8.22,13,8.5,13h2c0.28,0,0.5,0.22,0.5,0.5v2C11,15.78,10.78,16,10.5,16z M11,8.69 C11,9.41,10.45,10,9.71,10c-0.75,0-1.3-0.7-1.22-1.48L9.04,5H11V8.69z M15.5,18L15.5,18c-0.28,0-0.5-0.22-0.5-0.5V16h-1.5 c-0.28,0-0.5-0.22-0.5-0.5v-2c0-0.28,0.22-0.5,0.5-0.5h0c0.28,0,0.5,0.22,0.5,0.5V15h1v-1.5c0-0.28,0.22-0.5,0.5-0.5h0 c0.28,0,0.5,0.22,0.5,0.5v4C16,17.78,15.78,18,15.5,18z M18.77,10c-0.61,0-1.14-0.49-1.21-1.14L16.98,5l1.93-0.01l1.05,3.37 C20.12,9.03,19.71,10,18.77,10z"/></g>
  </svg>
</template>
        