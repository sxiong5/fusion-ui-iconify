
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ColorizeRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M20.71 5.63l-2.34-2.34c-.39-.39-1.02-.39-1.41 0l-3.12 3.12-1.23-1.21c-.39-.39-1.02-.38-1.41 0-.39.39-.39 1.02 0 1.41l.72.72-8.77 8.77c-.1.1-.15.22-.15.36v4.04c0 .28.22.5.5.5h4.04c.13 0 .26-.05.35-.15l8.77-8.77.72.72c.39.39 1.02.39 1.41 0 .39-.39.39-1.02 0-1.41l-1.22-1.22 3.12-3.12c.41-.4.41-1.03.02-1.42zM6.92 19L5 17.08l8.06-8.06 1.92 1.92L6.92 19z"/>
  </svg>
</template>
        