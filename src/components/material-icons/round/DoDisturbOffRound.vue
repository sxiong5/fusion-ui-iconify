
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DoDisturbOffRound',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M17 11v2h-.88l4.33 4.33C21.43 15.79 22 13.96 22 12c0-5.52-4.48-10-10-10-1.96 0-3.79.57-5.33 1.55L14.12 11H17zm4.17 9.88L3.12 2.83c-.39-.39-1.02-.39-1.41 0-.39.39-.39 1.02 0 1.41l2.07 2.07C2.66 7.93 2 9.89 2 12c0 5.52 4.48 10 10 10 2.11 0 4.07-.66 5.68-1.78l2.07 2.07c.39.39 1.02.39 1.41 0 .4-.39.4-1.02.01-1.41zM7 13v-2h1.46l2 2H7z"/>
  </svg>
</template>
        