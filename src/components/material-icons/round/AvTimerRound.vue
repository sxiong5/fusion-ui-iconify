
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AvTimerRound',
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
    <circle cx="12" cy="17" r="1"/><circle cx="7" cy="12" r="1"/><circle cx="17" cy="12" r="1"/><path d="M12 3c-.55 0-1 .45-1 1v2c0 .55.45 1 1 1s1-.45 1-1v-.92c3.31.48 5.87 3.25 6 6.66.14 3.85-3.03 7.2-6.88 7.26C8.19 19.06 5 15.91 5 12c0-1.68.59-3.22 1.58-4.42l4.71 4.72c.39.39 1.02.39 1.41 0 .39-.39.39-1.02 0-1.41L7.26 5.46c-.38-.38-1-.39-1.4-.02C4.1 7.07 3 9.4 3 12c0 5.04 4.14 9.12 9.21 9 4.7-.11 8.63-4.01 8.78-8.71C21.16 7.19 17.07 3 12 3z"/>
  </svg>
</template>
        