
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'Shop2Round',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M2,9L2,9c-0.55,0-1,0.45-1,1v10c0,1.1,0.9,2,2,2h15c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1H3V10C3,9.45,2.55,9,2,9z"/><path d="M18,5V3c0-1.11-0.89-2-2-2h-4c-1.11,0-2,0.89-2,2v2H5v11c0,1.11,0.89,2,2,2h14c1.11,0,2-0.89,2-2V5H18z M12,3h4v2h-4V3z M12,14.09V8.91c0-0.39,0.44-0.63,0.77-0.42l4.07,2.59c0.31,0.2,0.31,0.65,0,0.84l-4.07,2.59C12.44,14.72,12,14.48,12,14.09z"/></g></g>
  </svg>
</template>
        