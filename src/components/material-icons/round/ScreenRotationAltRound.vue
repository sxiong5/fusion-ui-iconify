
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ScreenRotationAltRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M18.53,9.29C19.16,9.92,18.71,11,17.82,11c-0.27,0-0.52-0.11-0.71-0.29L10.4,4L5.41,9H7c0.55,0,1,0.45,1,1s-0.45,1-1,1H3 c-0.55,0-1-0.45-1-1V6c0-0.55,0.45-1,1-1s1,0.45,1,1v1.59l5-5c0.78-0.78,2.05-0.78,2.83,0L18.53,9.29z"/><path d="M5.47,14.71C4.84,14.08,5.29,13,6.18,13c0.27,0,0.52,0.11,0.71,0.29L13.6,20l4.99-5H17c-0.55,0-1-0.45-1-1s0.45-1,1-1h4 c0.55,0,1,0.45,1,1v4c0,0.55-0.45,1-1,1s-1-0.45-1-1v-1.59l-5,5c-0.78,0.78-2.05,0.78-2.83,0L5.47,14.71z"/></g>
  </svg>
</template>
        