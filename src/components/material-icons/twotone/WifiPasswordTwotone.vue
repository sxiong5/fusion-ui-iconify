
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WifiPasswordTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M24,8.98l-2.12,2.13C19.35,8.57,15.85,7,12,7s-7.35,1.57-9.88,4.11L0,8.98C3.07,5.9,7.31,4,12,4S20.93,5.9,24,8.98z M24,20 v3c0,0.55-0.45,1-1,1h-4c-0.55,0-1-0.45-1-1v-3c0-0.55,0.45-1,1-1v-1c0-1.1,0.9-2,2-2s2,0.9,2,2v1C23.55,19,24,19.45,24,20z M22,18 c0-0.55-0.45-1-1-1s-1,0.45-1,1v1h2V18z M4.24,13.22l2.12,2.12C7.8,13.9,9.8,13,12,13c2.2,0,4.2,0.9,5.64,2.35l2.12-2.12 C17.78,11.23,15.03,10,12,10C8.97,10,6.22,11.23,4.24,13.22z M12,16c-1.38,0-2.63,0.56-3.53,1.46L12,21l3.53-3.54 C14.63,16.56,13.38,16,12,16z"/></g>
  </svg>
</template>
        