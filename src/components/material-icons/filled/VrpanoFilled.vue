
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'VrpanoFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M20.69,4.05C18.66,4.73,15.86,5.5,12,5.5c-3.89,0-6.95-0.84-8.69-1.43C2.67,3.85,2,4.33,2,5.02V19 c0,0.68,0.66,1.17,1.31,0.95C5.36,19.26,8.1,18.5,12,18.5c3.87,0,6.66,0.76,8.69,1.45C21.34,20.16,22,19.68,22,19V5 C22,4.32,21.34,3.84,20.69,4.05z M12,15c-2.34,0-4.52,0.15-6.52,0.41l3.69-4.42l2,2.4L14,10l4.51,5.4C16.52,15.15,14.3,15,12,15z"/></g>
  </svg>
</template>
        