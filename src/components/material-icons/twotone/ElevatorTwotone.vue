
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ElevatorTwotone',
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
    <g><rect fill="none" height="24" width="24"/><path d="M19,5v14H5V5H19 M10,18v-4h1v-2.5c0-1.1-0.9-2-2-2H8c-1.1,0-2,0.9-2,2V14h1v4H10z M8.5,8.5 c0.69,0,1.25-0.56,1.25-1.25S9.19,6,8.5,6S7.25,6.56,7.25,7.25S7.81,8.5,8.5,8.5z M18,11l-2.5-4L13,11H18z M13,13l2.5,4l2.5-4H13z" opacity=".3"/><path d="M19,5v14H5V5H19 M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3L19,3z M10,18v-4h1 v-2.5c0-1.1-0.9-2-2-2H8c-1.1,0-2,0.9-2,2V14h1v4H10z M8.5,8.5c0.69,0,1.25-0.56,1.25-1.25S9.19,6,8.5,6S7.25,6.56,7.25,7.25 S7.81,8.5,8.5,8.5z M18,11l-2.5-4L13,11H18z M13,13l2.5,4l2.5-4H13z"/></g>
  </svg>
</template>
        