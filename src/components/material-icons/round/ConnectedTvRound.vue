
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ConnectedTvRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M20,3H4C2.9,3,2,3.9,2,5v12c0,1.1,0.9,2,2,2h4v1c0,0.55,0.45,1,1,1h6c0.55,0,1-0.45,1-1v-1h4c1.1,0,1.99-0.9,1.99-2L22,5 C22,3.9,21.1,3,20,3z M20,17H4V5h16V17z M7,15.97C6.98,14.89,6.11,14.02,5.03,14H5v2h2V15.97z M5.62,12.55 c1.44,0.26,2.58,1.4,2.83,2.84C8.51,15.75,8.82,16,9.18,16h0c0.46,0,0.82-0.41,0.75-0.86c-0.36-2.07-1.99-3.7-4.06-4.06 C5.41,11,5,11.36,5,11.82v0C5,12.19,5.26,12.49,5.62,12.55z M5.64,9.53c3.07,0.3,5.52,2.75,5.83,5.82 c0.04,0.37,0.37,0.65,0.74,0.65c0.45,0,0.79-0.4,0.75-0.85c-0.4-3.74-3.37-6.71-7.11-7.1C5.4,8,5,8.34,5,8.79 C5,9.16,5.27,9.5,5.64,9.53z"/></g>
  </svg>
</template>
        