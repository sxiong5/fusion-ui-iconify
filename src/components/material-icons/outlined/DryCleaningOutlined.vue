
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DryCleaningOutlined',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><g><path d="M19.56,11.36L13,8.44V7c0-0.55-0.45-1-1-1l0,0c-0.55,0-1-0.45-1-1s0.45-1,1-1s1,0.45,1,1h2c0-1.84-1.66-3.3-3.56-2.95 C10.26,2.27,9.29,3.22,9.06,4.4C8.76,5.96,9.66,7.34,11,7.82v0.63l-6.56,2.92C3.56,11.75,3,12.62,3,13.57v0.01 C3,14.92,4.08,16,5.42,16H7v6h10v-6h1.58c1.34,0,2.42-1.08,2.42-2.42v-0.01C21,12.62,20.44,11.75,19.56,11.36z M15,20H9v-5h6V20z M18.58,14H17v-1H7v1H5.42c-0.46,0-0.58-0.65-0.17-0.81l6.75-3l6.75,3C19.17,13.38,19.03,14,18.58,14z"/></g></g>
  </svg>
</template>
        