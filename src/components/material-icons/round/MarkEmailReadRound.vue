
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MarkEmailReadRound',
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
    <g><g><rect fill="none" height="24" width="24" x="0"/></g><g><path d="M18.05,21.29c-0.39,0.39-1.02,0.39-1.41,0l-2.12-2.12c-0.39-0.39-0.39-1.02,0-1.41h0c0.39-0.39,1.02-0.39,1.41,0 l1.41,1.41l3.54-3.54c0.39-0.39,1.02-0.39,1.41,0l0,0c0.39,0.39,0.39,1.02,0,1.41L18.05,21.29z M12.08,20H4c-1.1,0-2-0.9-2-2V6 c0-1.1,0.9-2,2-2h16c1.1,0,2,0.9,2,2v6.68C21.09,12.25,20.08,12,19,12c-3.87,0-7,3.13-7,7C12,19.34,12.03,19.67,12.08,20z M11.47,12.67c0.32,0.2,0.74,0.2,1.06,0l7.07-4.42C19.85,8.09,20,7.82,20,7.53c0-0.67-0.73-1.07-1.3-0.72L12,11L5.3,6.81 C4.73,6.46,4,6.86,4,7.53c0,0.29,0.15,0.56,0.4,0.72L11.47,12.67z"/></g></g>
  </svg>
</template>
        