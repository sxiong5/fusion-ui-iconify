
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RawOffSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><polygon points="17.15,14.32 17.74,11.96 18.5,15 19.98,15 21.48,9 19.98,9 19.24,12 18.5,9 16.98,9 16.24,12 15.5,9 14,9 14.72,11.9"/><path d="M1.39,4.22L6.17,9H3v6h1.5v-2h1.1l0.9,2H8l-0.9-2.1C7.6,12.6,8,12.1,8,11.5v-0.67l1.43,1.43L8.75,15h1.5l0.38-1.5h0.04 l9.11,9.11l1.41-1.41L2.81,2.81L1.39,4.22z M6.5,11.5h-2v-1h2V11.5z"/></g></g>
  </svg>
</template>
        