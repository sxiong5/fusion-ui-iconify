
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AppShortcutRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M17,18H7V6h10v1h2V3c0-1.1-0.9-2-2-2H7C5.9,1,5,1.9,5,3v18c0,1.1,0.9,2,2,2h10c1.1,0,2-0.9,2-2v-4h-2V18z"/><path d="M20.38,9.62l0.4,0.87c0.09,0.2,0.37,0.2,0.46,0l0.4-0.87l0.87-0.4c0.2-0.09,0.2-0.37,0-0.46l-0.87-0.4l-0.4-0.87 c-0.09-0.2-0.37-0.2-0.46,0l-0.4,0.87l-0.87,0.4c-0.2,0.09-0.2,0.37,0,0.46L20.38,9.62z"/><path d="M15.54,9l-0.79,1.75L13,11.54c-0.39,0.18-0.39,0.73,0,0.91l1.75,0.79L15.54,15c0.18,0.39,0.73,0.39,0.91,0l0.79-1.75 L19,12.46c0.39-0.18,0.39-0.73,0-0.91l-1.75-0.79L16.46,9C16.28,8.61,15.72,8.61,15.54,9z"/><path d="M20.77,13.5l-0.4,0.87l-0.87,0.4c-0.2,0.09-0.2,0.37,0,0.46l0.87,0.4l0.4,0.87c0.09,0.2,0.37,0.2,0.46,0l0.4-0.87 l0.87-0.4c0.2-0.09,0.2-0.37,0-0.46l-0.87-0.4l-0.4-0.87C21.14,13.31,20.86,13.31,20.77,13.5z"/></g></g>
  </svg>
</template>
        