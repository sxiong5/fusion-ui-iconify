
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RawOnTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M6.5,9H3v6h1.5v-2h1.1l0.9,2H8l-0.9-2.1C7.6,12.6,8,12.1,8,11.5v-1C8,9.7,7.3,9,6.5,9z M6.5,11.5h-2v-1h2V11.5z"/><path d="M10.25,9l-1.5,6h1.5l0.38-1.5h1.75l0.37,1.5h1.5l-1.5-6H10.25z M11,12l0.25-1h0.5L12,12H11z"/><polygon points="19.98,9 19.24,12 18.5,9 16.98,9 16.24,12 15.5,9 14,9 15.5,15 16.98,15 17.74,11.96 18.5,15 19.98,15 21.48,9"/></g></g>
  </svg>
</template>
        