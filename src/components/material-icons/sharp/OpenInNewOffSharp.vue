
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'OpenInNewOffSharp',
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
    <rect fill="none" height="24" width="24"/><path d="M16.79,5.8L14,3h7v7l-2.79-2.8l-4.09,4.09l-1.41-1.41L16.79,5.8z M19,12v4.17l2,2V12H19z M19.78,22.61L18.17,21H3V5.83 L1.39,4.22l1.41-1.41l18.38,18.38L19.78,22.61z M16.17,19l-4.88-4.88L9.7,15.71L8.29,14.3l1.59-1.59L5,7.83V19H16.17z M7.83,5H12V3 H5.83L7.83,5z"/>
  </svg>
</template>
        