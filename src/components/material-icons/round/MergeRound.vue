
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MergeRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M8.71,7.71c-0.39-0.39-0.39-1.02,0-1.41l2.59-2.59c0.39-0.39,1.02-0.39,1.41,0l2.59,2.59c0.39,0.39,0.39,1.02,0,1.41 c-0.39,0.39-1.02,0.39-1.41,0L13,6.83v5.1c0,1.06,0.42,2.08,1.17,2.83l4.12,4.12c0.39,0.39,0.39,1.02,0,1.41s-1.02,0.39-1.41,0 L12,15.41l-4.88,4.88c-0.39,0.39-1.02,0.39-1.41,0c-0.39-0.39-0.39-1.02,0-1.41l4.12-4.12c0.75-0.75,1.17-1.77,1.17-2.83v-5.1 l-0.88,0.88C9.73,8.1,9.1,8.1,8.71,7.71z"/></g>
  </svg>
</template>
        