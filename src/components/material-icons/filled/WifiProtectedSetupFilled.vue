
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WifiProtectedSetupFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M16.71,5.29L19,3h-8v8l2.3-2.3c1.97,1.46,3.25,3.78,3.25,6.42c0,1.31-0.32,2.54-0.88,3.63c2.33-1.52,3.88-4.14,3.88-7.13 C19.55,9.1,18.44,6.85,16.71,5.29z"/></g><g><path d="M7.46,8.88c0-1.31,0.32-2.54,0.88-3.63C6,6.77,4.46,9.39,4.46,12.38c0,2.52,1.1,4.77,2.84,6.33L5,21h8v-8l-2.3,2.3 C8.74,13.84,7.46,11.52,7.46,8.88z"/></g></g></g>
  </svg>
</template>
        