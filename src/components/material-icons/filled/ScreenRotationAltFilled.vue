
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ScreenRotationAltFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M4,7.59l5-5c0.78-0.78,2.05-0.78,2.83,0L20.24,11h-2.83L10.4,4L5.41,9H8v2H2V5h2V7.59z M20,19h2v-6h-6v2h2.59l-4.99,5 l-7.01-7H3.76l8.41,8.41c0.78,0.78,2.05,0.78,2.83,0l5-5V19z"/></g>
  </svg>
</template>
        