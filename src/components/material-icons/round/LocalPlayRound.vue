
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LocalPlayRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M20 12c0-.76.43-1.42 1.06-1.76.6-.33.94-1.01.94-1.7V6c0-1.1-.9-2-2-2H4c-1.1 0-1.99.89-1.99 1.99v2.55c0 .69.33 1.37.94 1.69C3.58 10.58 4 11.24 4 12s-.43 1.43-1.06 1.76c-.6.33-.94 1.01-.94 1.7v2.25C2 19.1 2.9 20 4 20h16c1.1 0 2-.9 2-2v-2.54c0-.69-.34-1.37-.94-1.7-.63-.34-1.06-1-1.06-1.76zm-5.5 4.1L12 14.5l-2.5 1.61c-.38.24-.87-.11-.75-.55l.75-2.88-2.3-1.88c-.35-.29-.17-.86.29-.89l2.96-.17 1.08-2.75c.17-.42.77-.42.93 0l1.08 2.76 2.96.17c.45.03.64.6.29.89l-2.3 1.88.76 2.86c.12.45-.37.8-.75.55z"/>
  </svg>
</template>
        