
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DinnerDiningFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M2,19h20l-2,2H4L2,19z M5,6h1v1H5V6z M5,4h1v1H5V4z M9,4v1H7V4H9z M9,7H7V6h2V7z M6,15.23c-0.36,0.11-0.69,0.28-1,0.47V8h1 V15.23z M4,16.52C3.62,16.96,3.32,17.45,3.16,18h16.82c0.01-0.16,0.03-0.33,0.03-0.5c0-3.04-2.46-5.5-5.5-5.5 c-2.29,0-4.25,1.4-5.08,3.4C8.84,15.15,8.19,15,7.5,15c-0.17,0-0.33,0.02-0.5,0.04V8h2c1.03,0.06,1.9-0.96,2-2h10V5H11 c-0.1-1.05-0.97-1.97-2-2H3v1h1v1H3v1h1v1H3v1h1V16.52z"/></g>
  </svg>
</template>
        