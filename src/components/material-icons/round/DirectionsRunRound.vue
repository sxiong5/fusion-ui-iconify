
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DirectionsRunRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M13.49 5.48c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2zm-3.17 12l.57-2.5 2.1 2v5c0 .55.45 1 1 1s1-.45 1-1v-5.64c0-.55-.22-1.07-.62-1.45l-1.48-1.41.6-3c1.07 1.24 2.62 2.13 4.36 2.41.6.09 1.14-.39 1.14-1 0-.49-.36-.9-.85-.98-1.52-.25-2.78-1.15-3.45-2.33l-1-1.6c-.4-.6-1-1-1.7-1-.3 0-.5.1-.8.1L7.21 7.76c-.74.32-1.22 1.04-1.22 1.85v2.37c0 .55.45 1 1 1s1-.45 1-1v-2.4l1.8-.7-1.6 8.1-3.92-.8c-.54-.11-1.07.24-1.18.78V17c-.11.54.24 1.07.78 1.18l4.11.82c1.06.21 2.1-.46 2.34-1.52z"/>
  </svg>
</template>
        