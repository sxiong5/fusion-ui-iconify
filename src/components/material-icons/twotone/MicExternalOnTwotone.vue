
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MicExternalOnTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><polygon opacity=".3" points="6.81,16 7.19,16 7.79,10 6.21,10"/><path d="M9.22,7C9.7,6.47,10,5.77,10,5c0-1.66-1.34-3-3-3S4,3.34,4,5c0,0.77,0.3,1.47,0.78,2H9.22z"/><path d="M16,2c-2.21,0-4,1.79-4,4v12c0,1.1-0.9,2-2,2s-2-0.9-2-2h1l1-10H4l1,10h1c0,2.21,1.79,4,4,4s4-1.79,4-4V6c0-1.1,0.9-2,2-2 s2,0.9,2,2v16h2V6C20,3.79,18.21,2,16,2z M7.19,16H6.81l-0.6-6h1.58L7.19,16z"/></g></g>
  </svg>
</template>
        