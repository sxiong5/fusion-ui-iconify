
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'VaccinesSharp',
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
    <rect fill="none" height="24" width="24"/><path d="M12,5.5H8V4h1.5V2h-5v2H6v1.5H2v2c0,0,0.45,0,1,0V17h3v4l2,1.5V17h3V7.5c0.55,0,1,0,1,0V5.5z M9,9H6.5v1.5H9V12H6.5v1.5H9 L9,15H5V7.5h4V9z M19.5,10.5V10h1V8h-7l-0.01,2h1.01v0.5c0,0.5-1.5,1.16-1.5,3V22h8v-8.5C21,11.66,19.5,11,19.5,10.5z M16.5,10.5V10 h1v0.5c0,1.6,1.5,2,1.5,3V14h-4c0-0.21,0-0.39,0-0.5C15,12.5,16.5,12.1,16.5,10.5z M15,20c0,0,0-0.63,0-1.5h4V20H15z"/>
  </svg>
</template>
        