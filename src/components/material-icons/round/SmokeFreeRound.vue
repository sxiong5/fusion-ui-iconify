
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SmokeFreeRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M20.5 13H22v3h-1.5zM18 13h1.5v3H18zm-1 1.5c0-.83-.67-1.5-1.5-1.5h-.84l2.18 2.18c.1-.21.16-.44.16-.68zm1.96-12.15H19h-.04zm-.11 2.38c.38-.38.67-.84.84-1.35.16-.5-.19-1.01-.71-1.02-.34.01-.61.25-.72.58-.18.55-.62.99-1.17 1.17-.34.11-.59.39-.59.74V5c0 .37.27.69.64.75 1.93.31 3.36 2 3.36 4.02v1.48c0 .41.34.75.75.75s.75-.34.75-.75V9.76c0-2.22-1.28-4.14-3.15-5.03zm-4.24 3.92h1.42c1.05 0 1.97.74 1.97 2.05v.55c0 .41.33.75.75.75h.01c.41 0 .75-.33.75-.75v-.89c0-1.81-1.6-3.16-3.47-3.16h-1.3c-1.02 0-1.94-.73-2.07-1.75-.12-.95.46-1.7 1.3-1.93.32-.09.54-.38.54-.72 0-.49-.46-.86-.93-.72-1.42.41-2.45 1.73-2.42 3.28.02 1.85 1.61 3.29 3.45 3.29zM4.12 5.29c-.39-.39-1.02-.39-1.41 0-.39.39-.39 1.02 0 1.41L9 13H3.5c-.83 0-1.5.67-1.5 1.5S2.67 16 3.5 16H12l6.29 6.29c.39.39 1.02.39 1.41 0 .39-.39.39-1.02 0-1.41L4.12 5.29z"/>
  </svg>
</template>
        