
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SyncLockRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M10,19c0,0.55-0.45,1-1,1H5c-0.55,0-1-0.45-1-1v0c0-0.55,0.45-1,1-1h1.73C5.06,16.54,4,14.4,4,12 c0-3.19,1.87-5.93,4.56-7.22C9.23,4.47,10,4.96,10,5.7c0,0.38-0.22,0.72-0.57,0.88C7.41,7.55,6,9.61,6,12c0,1.77,0.78,3.34,2,4.44 V15c0-0.55,0.45-1,1-1h0c0.55,0,1,0.45,1,1V19z M15,4c-0.55,0-1,0.45-1,1v4c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1V7.56 c1.22,1.1,2,2.67,2,4.44h2c0-2.4-1.06-4.54-2.73-6H19c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1H15z M20,17v-1c0-1.1-0.9-2-2-2 s-2,0.9-2,2v1c-0.55,0-1,0.45-1,1v3c0,0.55,0.45,1,1,1h4c0.55,0,1-0.45,1-1v-3C21,17.45,20.55,17,20,17z M19,17h-2v-1 c0-0.55,0.45-1,1-1s1,0.45,1,1V17z"/></g>
  </svg>
</template>
        