
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TtyOutlined',
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
    <g><rect fill="none" height="24" width="24" x="0"/><path d="M16,6h-2V4h2V6z M18,7h-2v2h2V7z M19,9h2V7h-2V9z M19,4h-2v2h2V4z M15,7h-2v2h2V7z M19,10h-2v2h2V10z M16,10h-2v2h2V10z M13,4h-2v2h2V4z M20,15.82v4.15c0,0.56-0.47,1.03-1.03,1c-2.89-0.17-5.6-1.03-7.97-2.4C8.27,16.99,6.01,14.73,4.43,12 C3.05,9.63,2.2,6.92,2.03,4.03C2,3.47,2.47,3,3.03,3h4.15c0.48,0,0.89,0.34,0.98,0.8L8.9,7.48c0.07,0.33-0.04,0.67-0.27,0.9 L6.1,10.9c1.43,2.5,3.5,4.57,6,6l2.52-2.52c0.24-0.24,0.58-0.34,0.9-0.27l3.67,0.73C19.66,14.93,20,15.34,20,15.82z M5.18,8.99 l1.65-1.65L6.36,5H4.13C4.3,6.37,4.66,7.71,5.18,8.99z M18,16.64l-2.34-0.47l-1.65,1.65c1.28,0.52,2.63,0.87,3.99,1.05V16.64z M20,4v2h2V4H20z M20,12h2v-2h-2V12z M13,10h-2v2h2V10z"/></g>
  </svg>
</template>
        