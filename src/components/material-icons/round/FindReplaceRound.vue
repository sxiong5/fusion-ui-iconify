
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FindReplaceRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M11 6c1.38 0 2.63.56 3.54 1.46l-1.69 1.69c-.31.31-.09.85.36.85h4.29c.28 0 .5-.22.5-.5V5.21c0-.45-.54-.67-.85-.35l-1.2 1.2C14.68 4.78 12.93 4 11 4 7.96 4 5.38 5.94 4.42 8.64c-.24.66.23 1.36.93 1.36.42 0 .79-.26.93-.66C6.96 7.4 8.82 6 11 6zm5.64 9.14c.4-.54.72-1.15.95-1.8.23-.65-.25-1.34-.94-1.34-.42 0-.79.26-.93.66C15.04 14.6 13.18 16 11 16c-1.38 0-2.63-.56-3.54-1.46l1.69-1.69c.31-.31.09-.85-.36-.85H4.5c-.28 0-.5.22-.5.5v4.29c0 .45.54.67.85.35l1.2-1.2C7.32 17.22 9.07 18 11 18c1.55 0 2.98-.51 4.14-1.36l4.11 4.11c.41.41 1.08.41 1.49 0 .41-.41.41-1.08 0-1.49l-4.1-4.12z"/>
  </svg>
</template>
        