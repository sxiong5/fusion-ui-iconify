
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PhoneEnabledRound',
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
    <rect fill="none" height="24" width="24"/><g><g><path d="M4.78,15.27l2.54-0.29c0.61-0.07,1.21,0.14,1.64,0.57l1.84,1.84c2.83-1.44,5.15-3.75,6.59-6.59l-1.85-1.85 c-0.43-0.43-0.64-1.03-0.57-1.64l0.29-2.52c0.12-1.01,0.97-1.77,1.99-1.77h1.73c1.13,0,2.07,0.94,2,2.07 c-0.53,8.54-7.36,15.36-15.89,15.89c-1.13,0.07-2.07-0.87-2.07-2v-1.73C3.01,16.24,3.77,15.39,4.78,15.27z"/></g></g>
  </svg>
</template>
        