
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HeadphonesRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M3,12v7c0,1.1,0.9,2,2,2h2c1.1,0,2-0.9,2-2v-4c0-1.1-0.9-2-2-2H5v-1c0-3.87,3.13-7,7-7s7,3.13,7,7v1h-2c-1.1,0-2,0.9-2,2v4 c0,1.1,0.9,2,2,2h2c1.1,0,2-0.9,2-2v-7c0-4.97-4.03-9-9-9S3,7.03,3,12z"/></g>
  </svg>
</template>
        