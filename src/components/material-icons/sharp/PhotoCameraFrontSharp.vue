
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PhotoCameraFrontSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M16.83,5L15,3H9L7.17,5H2v16h20V5H16.83z M12,9c1.1,0,2,0.9,2,2c0,1.1-0.9,2-2,2s-2-0.9-2-2C10,9.9,10.9,9,12,9z M16,17H8 v-0.57c0-0.81,0.48-1.53,1.22-1.85C10.07,14.21,11.01,14,12,14s1.93,0.21,2.78,0.58C15.52,14.9,16,15.62,16,16.43V17z"/></g>
  </svg>
</template>
        