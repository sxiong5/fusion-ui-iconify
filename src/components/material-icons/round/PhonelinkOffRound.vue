
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PhonelinkOffRound',
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
    <path d="M24 19V9c0-.55-.45-1-1-1h-6c-.55 0-1 .45-1 1v3.61l2 2V10h4v7h-1.61l2.93 2.93c.39-.13.68-.49.68-.93zM21 6c.55 0 1-.45 1-1s-.45-1-1-1H7.39l2 2H21zM1.36 2.21c-.39.39-.39 1.02 0 1.41l1.11 1.11C2.18 5.08 2 5.52 2 6v11h-.5c-.83 0-1.5.67-1.5 1.5S.67 20 1.5 20h16.23l1.64 1.64c.39.39 1.02.39 1.41 0 .39-.39.39-1.02 0-1.41L2.77 2.21c-.39-.39-1.02-.39-1.41 0zM4 17V6.27L14.73 17H4z"/>
  </svg>
</template>
        