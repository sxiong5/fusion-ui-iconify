
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FamilyRestroomSharp',
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
    <g><rect fill="none" height="24" width="24"/><path d="M16,4c0-1.11,0.89-2,2-2s2,0.89,2,2s-0.89,2-2,2S16,5.11,16,4z M20,22v-6h2.5l-3-9l-3,0l-1.17,3.5H17V22H20z M12.5,11.5 c0.83,0,1.5-0.67,1.5-1.5s-0.67-1.5-1.5-1.5S11,9.17,11,10S11.67,11.5,12.5,11.5z M5.5,6c1.11,0,2-0.89,2-2s-0.89-2-2-2 s-2,0.89-2,2S4.39,6,5.5,6z M7.5,22v-7H9V7H2v8h1.5v7H7.5z M14,22v-4h1v-5.5h-5V18h1v4H14z"/></g>
  </svg>
</template>
        