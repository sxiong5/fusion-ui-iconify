
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LeaderboardRound',
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
    <rect fill="none" height="24" width="24"/><g><path d="M6.5,21H3c-0.55,0-1-0.45-1-1V10c0-0.55,0.45-1,1-1h3.5c0.55,0,1,0.45,1,1v10C7.5,20.55,7.05,21,6.5,21z M13.75,3h-3.5 c-0.55,0-1,0.45-1,1v16c0,0.55,0.45,1,1,1h3.5c0.55,0,1-0.45,1-1V4C14.75,3.45,14.3,3,13.75,3z M21,11h-3.5c-0.55,0-1,0.45-1,1v8 c0,0.55,0.45,1,1,1H21c0.55,0,1-0.45,1-1v-8C22,11.45,21.55,11,21,11z"/></g>
  </svg>
</template>
        