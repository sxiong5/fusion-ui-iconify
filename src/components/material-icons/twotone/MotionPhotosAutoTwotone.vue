
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MotionPhotosAutoTwotone',
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
    <rect fill="none" height="24" width="24"/><path d="M2.88,7.88l1.54,1.54C4.15,10.23,4,11.1,4,12c0,4.41,3.59,8,8,8s8-3.59,8-8s-3.59-8-8-8c-0.9,0-1.77,0.15-2.58,0.42 L7.89,2.89C9.15,2.32,10.54,2,12,2c5.52,0,10,4.48,10,10s-4.48,10-10,10S2,17.52,2,12C2,10.53,2.32,9.14,2.88,7.88z M7,5.5 C7,6.33,6.33,7,5.5,7S4,6.33,4,5.5S4.67,4,5.5,4S7,4.67,7,5.5z M12.03,8.99h-0.07l-1.16,3.31h2.39L12.03,8.99z M11.29,7.5h1.43 l3.01,8h-1.39l-0.72-2.04h-3.23L9.66,15.5H8.28L11.29,7.5z"/>
  </svg>
</template>
        