
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ElevatorSharp',
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
    <g><rect fill="none" height="24" width="24"/><path d="M21,3H3v18h18V3z M8.5,6c0.69,0,1.25,0.56,1.25,1.25c0,0.69-0.56,1.25-1.25,1.25S7.25,7.94,7.25,7.25 C7.25,6.56,7.81,6,8.5,6z M11,14h-1v4H7v-4H6V9.5h5V14z M15.5,17L13,13h5L15.5,17z M13,11l2.5-4l2.5,4H13z"/></g>
  </svg>
</template>
        