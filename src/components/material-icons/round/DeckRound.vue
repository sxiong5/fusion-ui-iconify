
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DeckRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M20.41,9c0.49,0,0.69-0.63,0.29-0.91L13.15,2.8c-0.69-0.48-1.61-0.48-2.29,0L3.3,8.09C2.9,8.37,3.1,9,3.59,9H11v12 c0,0.55,0.45,1,1,1s1-0.45,1-1V9H20.41z"/><path d="M8,16H4.9l-0.57-3.02c-0.1-0.54-0.62-0.9-1.17-0.8c-0.54,0.1-0.9,0.62-0.8,1.17L3,16.74V21c0,0.55,0.45,1,1,1h0.01 c0.55,0,1-0.44,1-0.99L5.02,18H7v3c0,0.55,0.45,1,1,1s1-0.45,1-1v-4C9,16.45,8.55,16,8,16z"/><path d="M20.84,12.18c-0.54-0.1-1.06,0.26-1.17,0.8L19.1,16H16c-0.55,0-1,0.45-1,1v4c0,0.55,0.45,1,1,1s1-0.45,1-1v-3h1.98 l0.02,3.01c0,0.55,0.45,0.99,1,0.99H20c0.55,0,1-0.45,1-1v-4.26l0.64-3.39C21.74,12.81,21.38,12.28,20.84,12.18z"/></g></g>
  </svg>
</template>
        