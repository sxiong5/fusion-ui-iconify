
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WindPowerFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><rect height="2" width="6" x="4" y="3"/><rect height="2" width="5" x="1" y="7"/><rect height="2" width="5" x="3" y="19"/><path d="M13.73,10.61c0.75,0.23,1.3,0.78,1.57,1.46l4.27-7.11c0.65-1.08,0.3-2.48-0.78-3.13c-0.87-0.52-1.99-0.41-2.73,0.29 l-3.43,3.21C12.23,5.7,12,6.23,12,6.78v3.93C12.36,10.56,12.98,10.38,13.73,10.61z"/><path d="M10.61,12.27c0.16-0.52,0.48-0.96,0.89-1.27H3.28C2.02,11,1,12.02,1,13.28c0,1.02,0.67,1.91,1.65,2.19l4.51,1.29 c0.53,0.15,1.1,0.08,1.58-0.21l2.69-1.61C10.66,14.32,10.3,13.27,10.61,12.27z"/><path d="M22.21,18.61l-2.28-4.1c-0.27-0.48-0.73-0.83-1.26-0.97l-3.18-0.8c0.03,0.32,0,0.66-0.1,0.99 c-0.32,1.06-1.28,1.77-2.39,1.77c-0.61,0-0.99-0.22-1-0.22V21c-1.1,0-2,0.9-2,2h6c0-1.1-0.9-2-2-2v-4.28l4.61,4.61 c0.89,0.89,2.33,0.89,3.22,0C22.55,20.61,22.71,19.5,22.21,18.61z"/><path d="M12.56,14.43c0.79,0.24,1.63-0.2,1.87-1c0.24-0.79-0.2-1.63-1-1.87c-0.79-0.24-1.63,0.2-1.87,1 C11.32,13.35,11.77,14.19,12.56,14.43z"/></g></g>
  </svg>
</template>
        