
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DynamicFeedRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M7,8L7,8C6.45,8,6,8.45,6,9v6c0,1.1,0.9,2,2,2h8c0.55,0,1-0.45,1-1l0,0c0-0.55-0.45-1-1-1H8V9C8,8.45,7.55,8,7,8z"/><path d="M20,3h-8c-1.1,0-2,0.9-2,2v6c0,1.1,0.9,2,2,2h8c1.1,0,2-0.9,2-2V5C22,3.9,21.1,3,20,3z M20,11h-8V7h8V11z"/><path d="M3,12L3,12c-0.55,0-1,0.45-1,1v6c0,1.1,0.9,2,2,2h8c0.55,0,1-0.45,1-1l0,0c0-0.55-0.45-1-1-1H4v-6C4,12.45,3.55,12,3,12z"/></g></g></g>
  </svg>
</template>
        