
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BiotechRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M7,19c-1.1,0-2,0.9-2,2h14c0-1.1-0.9-2-2-2h-4v-2h3c1.1,0,2-0.9,2-2h-8c-1.66,0-3-1.34-3-3c0-1.09,0.59-2.04,1.46-2.56 C8.17,9.03,8,8.54,8,8c0-0.21,0.04-0.42,0.09-0.62C6.28,8.13,5,9.92,5,12c0,2.76,2.24,5,5,5v2H7z"/><path d="M10.56,5.51C11.91,5.54,13,6.64,13,8c0,0.75-0.33,1.41-0.85,1.87l0.25,0.68c0.19,0.52,0.76,0.79,1.28,0.6 c0.19,0.52,0.76,0.79,1.28,0.6c0.52-0.19,0.79-0.76,0.6-1.28c0.52-0.19,0.79-0.76,0.6-1.28L14.1,3.54 c-0.19-0.52-0.76-0.79-1.28-0.6c-0.19-0.52-0.76-0.79-1.28-0.6c-0.52,0.19-0.79,0.76-0.6,1.28c-0.52,0.19-0.79,0.76-0.6,1.28 L10.56,5.51z"/><circle cx="10.5" cy="8" r="1.5"/></g></g>
  </svg>
</template>
        