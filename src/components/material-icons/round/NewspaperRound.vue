
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NewspaperRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M21.15,3.85l-0.82,0.82l-0.95-0.96c-0.39-0.39-1.02-0.39-1.42,0L17,4.67l-0.96-0.96c-0.39-0.39-1.03-0.39-1.42,0 l-0.95,0.96l-0.96-0.96c-0.39-0.39-1.02-0.39-1.41,0l-0.96,0.96L9.38,3.71c-0.39-0.39-1.02-0.39-1.42,0L7,4.67L6.04,3.71 c-0.39-0.39-1.03-0.39-1.42,0L3.67,4.67L2.85,3.85C2.54,3.54,2,3.76,2,4.21V19c0,1.1,0.9,2,2,2l16,0c1.1,0,2-0.9,2-2V4.21 C22,3.76,21.46,3.54,21.15,3.85z M11,19H4v-6h7V19z M20,19h-7v-2h7V19z M20,15h-7v-2h7V15z M20,11H4V8h16V11z"/></g>
  </svg>
</template>
        