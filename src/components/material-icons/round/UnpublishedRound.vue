
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'UnpublishedRound',
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
    <rect fill="none" height="24" width="24"/><path d="M20.49,20.49L3.51,3.51c-0.39-0.39-1.02-0.39-1.41,0l0,0c-0.39,0.39-0.39,1.02,0,1.41l1.56,1.56 c-1.25,1.88-1.88,4.21-1.59,6.7c0.53,4.54,4.21,8.22,8.74,8.74c2.49,0.29,4.81-0.34,6.7-1.59l1.56,1.56c0.39,0.39,1.02,0.39,1.41,0 l0,0C20.88,21.51,20.88,20.88,20.49,20.49z M9.88,15.89l-2.83-2.83c-0.39-0.39-0.39-1.02,0-1.41l0,0c0.39-0.39,1.02-0.39,1.41,0 l2.12,2.12l0.18-0.18l1.41,1.41l-0.88,0.88C10.9,16.28,10.27,16.28,9.88,15.89z M13.59,10.76l-7.1-7.1c1.88-1.25,4.21-1.88,6.7-1.59 c4.54,0.53,8.22,4.21,8.74,8.74c0.29,2.49-0.34,4.82-1.59,6.7l-5.34-5.34l1.94-1.94c0.39-0.39,0.39-1.02,0-1.41v0 c-0.39-0.39-1.02-0.39-1.41,0L13.59,10.76z"/>
  </svg>
</template>
        