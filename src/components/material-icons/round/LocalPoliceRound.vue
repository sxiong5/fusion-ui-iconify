
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LocalPoliceRound',
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
    <rect fill="none" height="24" width="24"/><path d="M14.5,12.59l0.63,2.73c0.1,0.43-0.37,0.77-0.75,0.54L12,14.42l-2.39,1.44c-0.38,0.23-0.85-0.11-0.75-0.54L9.5,12.6 l-2.1-1.81C7.06,10.5,7.24,9.95,7.68,9.91l2.78-0.24l1.08-2.56c0.17-0.41,0.75-0.41,0.92,0l1.08,2.55l2.78,0.24 c0.44,0.04,0.62,0.59,0.28,0.88L14.5,12.59z M4.19,4.47C3.47,4.79,3,5.51,3,6.3V11c0,5.55,3.84,10.74,9,12c5.16-1.26,9-6.45,9-12 V6.3c0-0.79-0.47-1.51-1.19-1.83l-7-3.11c-0.52-0.23-1.11-0.23-1.62,0L4.19,4.47z"/>
  </svg>
</template>
        