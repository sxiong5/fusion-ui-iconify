
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ContentCutRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M9.64 7.64c.29-.62.42-1.33.34-2.09-.19-1.73-1.54-3.2-3.26-3.49-2.77-.48-5.14 1.89-4.66 4.65.3 1.72 1.76 3.07 3.49 3.26.76.08 1.46-.05 2.09-.34L10 12l-2.36 2.36c-.62-.29-1.33-.42-2.09-.34-1.73.19-3.2 1.54-3.49 3.26-.48 2.77 1.89 5.13 4.65 4.65 1.72-.3 3.07-1.76 3.26-3.49.08-.76-.05-1.46-.34-2.09L12 14l7.59 7.59c.89.89 2.41.26 2.41-1v-.01c0-.37-.15-.73-.41-1L9.64 7.64zM6 8c-1.1 0-2-.89-2-2s.9-2 2-2 2 .89 2 2-.9 2-2 2zm0 12c-1.1 0-2-.89-2-2s.9-2 2-2 2 .89 2 2-.9 2-2 2zm6-7.5c-.28 0-.5-.22-.5-.5s.22-.5.5-.5.5.22.5.5-.22.5-.5.5zm7.59-10.09L13 9l2 2 6.59-6.59c.26-.26.41-.62.41-1V3.4c0-1.25-1.52-1.88-2.41-.99z"/>
  </svg>
</template>
        