
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FrontLoaderFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="m19.5 6.5-1.91 1.91c-.38.38-.59.89-.59 1.42V11h-1V7c0-1.66-1.34-3-3-3H8v5H3c-1.1 0-2 .9-2 2v5.85c0 1.58 1.16 3.01 2.74 3.14a2.99 2.99 0 003.07-1.98l4.37-.01a2.979 2.979 0 003.41 1.94 3.013 3.013 0 002.35-2.39c.2-1.11-.22-2.11-.95-2.77V13h1c0 1.1.9 2 2 2h5L19.5 6.5zM4 18c-.55 0-1-.45-1-1s.45-1 1-1 1 .45 1 1-.45 1-1 1zm6-12h3c.55 0 1 .45 1 1v4h-4V6zm4 12c-.55 0-1-.45-1-1s.45-1 1-1 1 .45 1 1-.45 1-1 1z"/></g>
  </svg>
</template>
        