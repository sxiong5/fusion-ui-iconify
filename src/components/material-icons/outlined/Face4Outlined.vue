
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'Face4Outlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M12,2c-0.96,0-1.88,0.14-2.75,0.39C8.37,0.96,6.8,0,5,0C2.24,0,0,2.24,0,5c0,1.8,0.96,3.37,2.39,4.25 C2.14,10.12,2,11.04,2,12c0,5.52,4.48,10,10,10s10-4.48,10-10S17.52,2,12,2z M12,4c2.9,0,5.44,1.56,6.84,3.88 C18.41,7.95,17.96,8,17.5,8c-2.9,0-5.44-1.56-6.84-3.88h0C11.09,4.05,11.54,4,12,4z M4.42,9.47L4.42,9.47 C5.05,7.58,6.37,6,8.08,5.03C7.45,6.92,6.13,8.5,4.42,9.47z M2,5c0-1.65,1.35-3,3-3c0.95,0,1.8,0.46,2.35,1.15 C5.56,4.09,4.09,5.56,3.15,7.35C2.46,6.8,2,5.95,2,5z M12,20c-4.41,0-8-3.59-8-8c0-0.05,0.01-0.1,0.01-0.15 c2.6-0.98,4.68-2.99,5.74-5.55C11.58,8.56,14.37,10,17.5,10c0.75,0,1.47-0.09,2.17-0.24C19.88,10.47,20,11.22,20,12 C20,16.41,16.41,20,12,20z"/><circle cx="9" cy="13" r="1.25"/><circle cx="15" cy="13" r="1.25"/></g></g>
  </svg>
</template>
        