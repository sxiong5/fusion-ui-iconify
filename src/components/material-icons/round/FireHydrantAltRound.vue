
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FireHydrantAltRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M19,11h-1V8h1c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-1.35C16.83,3.67,14.61,2,12,2S7.17,3.67,6.35,6H5 C4.45,6,4,6.45,4,7v0c0,0.55,0.45,1,1,1h1v3H5c-1.1,0-2,0.9-2,2v2c0,1.1,0.9,2,2,2h1v3H5c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1 h14c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-1v-3h1c1.1,0,2-0.9,2-2v-2C21,11.9,20.1,11,19,11z M12,17.5c-1.93,0-3.5-1.57-3.5-3.5 s1.57-3.5,3.5-3.5s3.5,1.57,3.5,3.5S13.93,17.5,12,17.5z"/><circle cx="12" cy="14" r="1.5"/></g></g>
  </svg>
</template>
        