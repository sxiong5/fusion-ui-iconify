
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FlatwareRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M16,7.08c0,1.77-0.84,3.25-2,3.82V20c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1v-9.1c-1.16-0.57-2-2.05-2-3.82 C10.01,4.83,11.35,3,13,3C14.66,3,16,4.83,16,7.08z M18.27,3.18C17.64,2.99,17,3.49,17,4.15L17,20c0,0.55,0.45,1,1,1h0 c0.55,0,1-0.45,1-1v-7h1c0.55,0,1-0.45,1-1V7C21,5.54,20.14,3.74,18.27,3.18z M8.28,3c-0.4,0-0.72,0.32-0.72,0.72V7H6.72V3.72 C6.72,3.32,6.4,3,6,3S5.28,3.32,5.28,3.72V7H4.44V3.72C4.44,3.32,4.12,3,3.72,3S3,3.32,3,3.72V9c0,1.1,0.9,2,2,2v9 c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-9c1.1,0,2-0.9,2-2V3.72C9,3.32,8.68,3,8.28,3z"/></g>
  </svg>
</template>
        