
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TransgenderRound',
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
    <rect fill="none" height="24" width="24"/><path d="M21.5,1h-4c-0.55,0-1,0.45-1,1c0,0.55,0.45,1,1,1h1.58l-3.97,3.97C14.23,6.36,13.16,6,12,6S9.77,6.36,8.89,6.97L8.24,6.32 l0.7-0.7c0.39-0.39,0.39-1.02,0-1.41c-0.39-0.39-1.02-0.39-1.41,0l-0.7,0.7L4.92,3H6.5c0.55,0,1-0.45,1-1c0-0.55-0.45-1-1-1h-4 c-0.55,0-1,0.45-1,1v4c0,0.55,0.45,1,1,1s1-0.45,1-1V4.42l1.91,1.9L4.7,7.03c-0.39,0.39-0.39,1.02,0,1.41s1.02,0.39,1.41,0 l0.71-0.71l0.65,0.65C6.86,9.27,6.5,10.34,6.5,11.5c0,2.7,1.94,4.94,4.5,5.41V19h-1c-0.55,0-1,0.45-1,1c0,0.55,0.45,1,1,1h1v1 c0,0.55,0.45,1,1,1s1-0.45,1-1v-1h1c0.55,0,1-0.45,1-1c0-0.55-0.45-1-1-1h-1v-2.09c2.56-0.47,4.5-2.71,4.5-5.41 c0-1.16-0.36-2.23-0.97-3.12l3.97-3.96V6c0,0.55,0.45,1,1,1s1-0.45,1-1V2C22.5,1.45,22.05,1,21.5,1z M12,15 c-1.93,0-3.5-1.57-3.5-3.5C8.5,9.57,10.07,8,12,8s3.5,1.57,3.5,3.5C15.5,13.43,13.93,15,12,15z"/>
  </svg>
</template>
        